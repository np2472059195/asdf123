<template>
    <div class="left">
        <ul>
            <li v-for="(item,index) in options" :class="{'act':i==index}" :key="index" @click="menuBtn(item.value,index)">{{item.name}}</li>
        </ul>
    </div>
</template>

<script>
export default {
    data(){
        return{
            i:0
        }
    },
    props:["options"],
    methods:{
        menuBtn(item,index){
            console.log(item)
            this.i=index;
            this.$bus.$emit('addEvent',item)
        }
    }
}
</script>

<style>
.left{
    width: 100px;
    height: 100%;
    background:#eee;
}
.left ul li{
    height: 50px;
    line-height: 50px;
    text-align: center;
}
.act{
    background:green;
    color:blue;
}
</style>
