<template>
    <div>
        <h2>Caricamento in corso...</h2>
    </div>
</template>

<script>
export default {
    name: 'LoadVue'
}
</script>

<style  scoped lang="scss">
@import "../assets/style/vars.scss";

div {
    background-color: $backgroundColorElements;
    padding: 20px;
    border-radius: 20px;

    h2 {
        color: $colorTextPrimary;
    }
}
</style>