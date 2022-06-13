<template>
    <section>
        <div v-if="loading" class="d-flex justify-content-center">
            <Load />
        </div>
        <div v-else>
            <div class="d-flex justify-content-center mb-4">
                <Select />
            </div>
            <div class="d-flex flex-wrap">
                <CardSong v-for="(song, index) in songsList" :key="index" :item="song" />
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