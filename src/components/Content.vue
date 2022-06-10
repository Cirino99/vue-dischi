<template>
    <section class="d-flex flex-wrap">
        <CardSong v-for="(song,index) in songsList" :key="index" :item="song" />
    </section>
</template>

<script>
import CardSong from './CardSong.vue';
import axios from 'axios'

export default {
    name: "ContentVue",
    components: { CardSong },
    data(){
        return {
            apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
            songsList: []
        }
    },
    created(){
        this.getSongsData();
    },
    methods: {
        getSongsData(){
            axios.get(this.apiUrl).then((result)=>{
                this.songsList = result.data.response;
                console.log(this.songsList);
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