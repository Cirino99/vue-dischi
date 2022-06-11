<template>
    <section>
        <div v-if="loading" class="d-flex justify-content-center">
            <Load />
        </div>
        <div v-else class="d-flex flex-wrap">
            <CardSong v-for="(song, index) in songsList" :key="index" :item="song" />
        </div>
    </section>
</template>

<script>
import CardSong from './CardSong.vue';
import axios from 'axios'
import Load from './Load.vue';

export default {
    name: "ContentVue",
    components: { CardSong, Load },
    data() {
        return {
            apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
            songsList: [],
            loading: true
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
            });
        }
    }
}
</script>

<style scoped lang="scss">
section {
    width: 70%;
    margin: 60px auto;
}
</style>