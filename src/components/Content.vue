<template>
    <section>
        <div v-if="loading" class="d-flex justify-content-center">
            <Load />
        </div>
        <div v-else>
            <div class="d-flex justify-content-center align-items-center mb-4">
                <span>Genere:</span>
                <Select @mySelect="changeSelectGenere" :selectItem="genereListSongs" />
                <span>Autore:</span>
                <Select @mySelect="changeSelectAuthor" :selectItem="authorListSongs" />
            </div>
            <div class="d-flex flex-wrap">
                <CardSong v-for="(song, index) in filterSongs" :key="index" :item="song" />
            </div>
        </div>
    </section>
</template>

<script>
import CardSong from './CardSong.vue';
import axios from 'axios'
import Load from './Load.vue';
import Select from './Select.vue';

export default {
    name: "ContentVue",
    components: { CardSong, Load, Select },
    data() {
        return {
            apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
            songsList: [],
            loading: true,
            selectGenere: 'All',
            selectAuthor: 'All',
            genereListSongs: ['All'],
            authorListSongs: ['All']
        }
    },
    created() {
        this.getSongsData();
    },
    methods: {
        getSongsData() {
            axios.get(this.apiUrl).then((result) => {
                this.songsList = result.data.response;
                this.loading = false;
                this.searchGenereSongs();
                this.searchAuthorSongs();
            }).catch((error) => {
                console.log('Errore', error);
            });
        },
        changeSelectGenere(e) {
            this.selectGenere = e;
        },
        changeSelectAuthor(e) {
            this.selectAuthor = e;
        },
        searchGenereSongs() {
            this.songsList.forEach(element => {
                if (!this.genereListSongs.includes(element.genre))
                    this.genereListSongs.push(element.genre);
            });
        },
        searchAuthorSongs() {
            this.songsList.forEach(element => {
                if (!this.authorListSongs.includes(element.author))
                    this.authorListSongs.push(element.author);
            });
        }
    },
    computed: {
        filterSongs() {
            if (this.selectGenere === 'All') {
                if (this.selectAuthor === 'All') {
                    return this.songsList;
                } else {
                    return this.songsList.filter(item => {
                        return item.author.toLowerCase().includes(this.selectAuthor.toLowerCase());
                    });
                }
            } else {
                if (this.selectAuthor === 'All') {
                    return this.songsList.filter(item => {
                        return item.genre.toLowerCase().includes(this.selectGenere.toLowerCase());
                    });
                } else {
                    return this.songsList.filter(item => {
                        if (item.genre.toLowerCase().includes(this.selectGenere.toLowerCase()) && item.author.toLowerCase().includes(this.selectAuthor.toLowerCase())) {
                            return item;
                        }
                    });
                }
            }
        }
    }
}
</script>

<style scoped lang="scss">
@import "../assets/style/vars.scss";

section {
    width: 70%;
    margin: 60px auto;

    div {
        div {
            span {
                color: $colorTextPrimary;
                font-size: 18px;
                padding: 0 10px;
            }
        }
    }
}
</style>