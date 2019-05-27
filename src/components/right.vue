<template>
    <div class="right">
        <dl v-for="(item,index) in bodyList" :key="index">
            <dt><img :src="item.fontImg" alt=""></dt>
            <dd>
                <p class="title">{{item.title}}</p>
                <p><span>月售:{{item.good.sale}}</span><span>赞：{{item.good.zan}}</span></p>
                <p class="price">￥：{{item.price}}</p>
                <p class="jsnum"><span class="prev" v-if="item.count" @click="item.count--">-</span><span v-if="item.count">{{item.count}}</span><span class="add" @click="addFun(item,index)">+</span></p>
            </dd>
        </dl>
    </div>
</template>

<script>
export default {
data(){
    return{
        bodyList:[],
        menuSelecter:null
    }
},
props:["options","menuDefault"],
created(){
    this.bodyList = this.options[this.menuDefault].list;
    this.menuSelecter=this.menuDefault;
    this.$bus.$on('addEvent',(val)=>{
        this.bodyList=this.options[val].list;
        this.menuSelecter=val;
    })
},
methods:{
    addFun(item,index){
        item.count++;
        this.$bus.$emit('toFootercom',item,index,this.menuSelecter)
    }
}
}
</script>

<style scoped>
.title{
    font-weight: 900;
    font-size:20px;
}
.right img{
    height: 100px;
    width: 100px;
}
.right dl{
    display: flex;
}
input{
    width: 30px;
    text-align: center
}
.jsnum{
    display: flex;
    width: 100px;
}
.add,.prev{
    display: inline-block;
    border:2px solid black;
    width: 20px;
    height: 20px;
    line-height: 16px;
    text-align: center;
    border-radius:50%;
    margin: 0 5px;
}
</style>
