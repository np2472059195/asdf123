<template>
    <nav>
        <ul>
            <li v-for="(item,index) in navData" @click="changeActive(index)" :class="{'active':i==index}" :key="index">{{item.title}}</li>
        </ul> 
    </nav>
</template>

<script>
export default {
    data(){
        return{
            navData:[
                {"title":"点菜","value":"0"},
                {"title":"评论","value":"1"},
                {"title":"商家","value":"2"}
            ],
            i:0
        }
    },
    methods:{
        changeActive(index){
            this.i=index
        }
    }
}
</script>

<style>
    nav{
        height: 40px;
        width: 100%;
        background:#ccc;
    }
    nav ul{
        display: flex;
    }
    nav ul li{
        width: 33.33%;
        height: 100%;
        line-height: 40px;
        text-align: center
    }
    .active{
        background:red;
        color:white;
    }
</style>
