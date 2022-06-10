<template>
    <div class="card-song">
        <img :src="item.poster" :alt="item.title">
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
</style>