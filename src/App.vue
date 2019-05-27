<template>
  <div id="app">
    <Headercom></Headercom>
    <Navcom></Navcom>
    <Swipercom></Swipercom>
    <Bodycom></Bodycom>
    <Footercom></Footercom>
    <Covercom></Covercom>
  </div>
</template>

<script>
import "./font/iconfont.css";
import Headercom from './components/headercom.vue'
import Navcom from './components/navcom.vue'
import Swipercom from "./components/swipercom.vue"
import Bodycom from './components/bodycom.vue'
import Footercom from './components/footercom.vue'
import Covercom from './components/covercom.vue'
export default {
  name: 'App',
  components: {
    Headercom,
    Navcom,
    Bodycom,
    Footercom,
    Covercom,
    Swipercom
  }
}
</script>

<style>
*{
  padding: 0;
  margin: 0;
  list-style: none;
  text-decoration: none;
  box-sizing: border-box
}
#app{
  display: flex;
  flex-direction: column
}
html,body,#app{
  width: 100%;
  height: 100%;
}
</style>
