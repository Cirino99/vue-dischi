<template>
    <div>
        <select class="my-select" name="genere">
            <option value="all">All</option>
            <option value="rock">Rock</option>
            <option value="pop">Pop</option>
            <option value="jazz">Jazz</option>
            <option value="metal">Metal</option>
        </select>
    </div>
</template>

<script>
export default {
    name: 'SelectVue'
}
</script>

<style  scoped lang="scss">
@import "../assets/style/vars.scss";

div {

    .my-select {
        display: flex;
        align-items: center;
        height: 40px;
        width: 100px;
        background-color: $backgroundColorElements;
        color: $colorTextPrimary;
        border: .5px solid $colorTextSecondary;
        border-radius: 5px;
    }
}
</style>