<template>
    <div id="app">
        <Header/>
        <Content/>
    </div>
</template>

<script>
import Header from "./components/Header.vue";
import Content from "./components/Content.vue";


export default {
    name: 'App',
    components: {
    Header,
    Content
}
}
</script>

<style lang="scss">
@import "../node_modules/bootstrap/scss/bootstrap.scss";

#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
}
</style>
