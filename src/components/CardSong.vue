<template>
    <div class="card-song text-center">
        <img :src="item.poster" :alt="item.title">
        <h3>{{item.title}}</h3>
        <span>{{item.author}} <br> {{item.year}}</span>
    </div>
</template>

<script>
export default {
    name: 'CardSongVue',
    props: {
        item: Object
    }
}
</script>

<style scoped lang="scss">
.card-song {
    width: calc((100% /5) - 40px);
    background-color: #2e3a46;
    margin: 0 20px;
    margin-bottom: 20px;
    padding: 20px;
    
    img {
        width: 100%;
    }

    h3 {
        color: white;
        font-weight: 600;
        margin-top: 20px;
    }

    span {
        color: #897f78;
        font-size: 18px;
        font-weight: 500;
    }
}
</style>