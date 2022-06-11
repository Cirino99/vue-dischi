<template>
    <div id="app">
        <Header />
        <Content />
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
@import "./assets/style/vars.scss";

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    background-color: $backgroundColorPrimary;
    height: 100vh;
    width: 100%;
    overflow: auto;
}
</style>
