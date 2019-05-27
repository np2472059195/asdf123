<template>
    <div class="swiper-container">
        <swiper class="swiper" :options="swiperOptions">
          <swiper-slide class="swiper-slide" v-for="(item,index) in listSwiper" :key="index">
              <img :src="require('../../static/images/'+item.img)" alt="">
          </swiper-slide>
        </swiper>
    </div>
</template>

<script>
import 'swiper/dist/css/swiper.css'
 
import { swiper, swiperSlide } from 'vue-awesome-swiper'
export default {
    data(){
        return{
            listSwiper:[
                {img:"pic1.jpg"},
                {img:"pic2.jpg"},
                {img:"333.jpg"}
            ],
            swiperOptions:{
                autoplay:true,
                spped:500,
                loop:true,
                effect:"slide"
            }
        }
    },
  components: {
    swiper,
    swiperSlide
  }
}
</script>

<style>
.swiper-container{
    height: 100px;
    width: 100%;
    overflow: hidden
}
.swiper-container img{
    width: 100%;
    height: 100px;
}
</style>
