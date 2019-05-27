<template>
    <div class="cover" v-if="options.visible">
        <div class="cover-con">
            <div class="list-item" v-for="(item,index) in options.data" :key="index">
                <span>{{item.title}}</span><span>{{item.price}}</span>
                <p><span @click="item.count--">-</span> <span>{{item.count}}</span><span @click="item.count++">+</span></p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props:["options"],
    created(){
        this.$bus.$on('showCover',(val)=>{
            this.options.visible = !this.options.visible;
            this.options.data = val;
        })
    }
}

</script>

<style>
 .cover{
     position:absolute;
     top:0;
     bottom:10px;
     left: 0;
     right: 0;
     background: rgba(0,0,0,.4);
    }
.cover-con{
         width: 100%;
         background: white;
         position: absolute;
         bottom: 0;
    }
    .list-item{
             display: flex;
             justify-content: space-between;
             height: 10px;
             line-height: 10px;

         }
</style>
