<template>
    <div>
        <select class="my-select" name="genere" v-model="selected">
            <option v-for="(value, index) in selectItem" :key="index" @click="sendSelectValue">{{ value }}</option>
        </select>
    </div>
</template>

<script>
export default {
    name: 'SelectVue',
    data() {
        return {
            selected: 'All'
        }
    },
    props: {
        selectItem: Array
    },
    methods: {
        sendSelectValue() {
            this.$emit('mySelect', this.selected);
        }
    }
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