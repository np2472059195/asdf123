<template>
    <footer>
        <div class="num">
            数量：{{total}}
        </div>
        <div class="sumPrice" @click="showCover">
            结算：{{totalPrice}}
        </div>
    </footer>
</template>

<script>
export default {
    data(){
        return{
            footList:[],
            obj:{},
        }
    },
    props:["data"],
    created(){
        this.$bus.$on('toFootercom',(val,index,menuSelecter)=>{
            if(!this.obj[menuSelecter+index]&&this.obj[menuSelecter+index]!==0){
                this.footList.push(val);
                this.obj[menuSelecter+index]=this.footList.length-1;
            }else{
                let index = this.obj[menuSelecter+index];
                this.footList.splice(index,1,val)
            }
        })
    },
    computed:{
        total(){
            return this.footList.reduce((total,current)=>{
                return total+current.count
            },0)
        },
        totalPrice(){
            return this.footList.reduce((total,current)=>{
                return total+current.count*current.price
            },0)
        }
    },
    methods:{
        showCover(){
            this.$bus.$emit('showCover',this.footList)
        }
    }
}
</script>

<style scoped>
footer{ 
    display: flex;
    width: 360px;
    height: 50px;
}
footer div{
    width: 50%;
    text-align: center;
    line-height: 50px;
}
.num{
    background:#ccc;
}
.sumPrice{
    background:red;
}
</style>
