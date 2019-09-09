<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
  </div>
</template>
<script>
import HomeHeader from './components/Header'// import xx  xx是组件暴露出的接口名 from里的路径是组件名
import HomeSwiper from './components/Swiper'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper
  }
}
</script>
<style>
div {
  font-size: 30px;
}
</style>
