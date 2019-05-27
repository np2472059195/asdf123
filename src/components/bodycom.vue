<template>
    <section>
        <left :options="leftData.menu"></left>
        <right :options="rightData.data" :menuDefault="leftData.menu[0].value"></right>
    </section>
</template>

<script>
import left from "./left.vue";
import right from "./right.vue";
import leftData from "../data/menu.json";
import rightData from "../data/data.json";
export default {
    data(){
        return{
            leftData,
            rightData
        }
    },
    components:{
        left,
        right
    }
}
</script>

<style>
section{
    display: flex;
    height: 100%;
    width: 100%;
}
</style>
