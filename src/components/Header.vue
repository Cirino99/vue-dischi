<template>
    <header>
        <img src="../assets/img/logo-small.svg" alt="logo">
    </header>
</template>

<script>
export default {
    name: 'HeaderVue'
}
</script>

<style scoped lang="scss">
@import "../assets/style/vars.scss";

header {
    background-color: $backgroundColorElements;
    padding: 10px;

    img {
        width: 45px;
    }
}
</style>