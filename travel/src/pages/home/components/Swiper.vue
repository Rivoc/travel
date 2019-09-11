<template>
  <div class="wrapper">
    <swiper :options="swiperOption"
            v-if="showList">
      <!-- slides -->
      <swiper-slide v-for="item of swiperList"
                    :key="item.id">
        <img :src="item.imgUrl"
             class="swiper-img">
      </swiper-slide>
      <!-- 圆点 -->
      <div class="swiper-pagination"
           slot="pagination"></div>

      <!-- 左右箭头 -->
      <!-- <div class="swiper-button-prev"
         slot="button-prev"></div>
    <div class="swiper-button-next"
         slot="button-next"></div> -->
      <!-- 底部的滚动条 -->
      <!-- <div class="swiper-scrollbar"
         slot="scrollbar"></div> -->
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeSwiper',
  props: {
    swiperList: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: 2000,
        autoplayDisableOnInteraction: false//  触摸后重新启动autoplay
      }
    }
  },
  computed: {
    showList () {
      return this.swiperList.length
    }
  }
}
</script>
<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active {
  background: #fff;
}

.wrapper {
  width: 100%;
  // height: 26.6vw;
  height: 0;
  padding-bottom: 26.6%; // padding相对于父元素的宽来计算
  background-color: #eee;
  overflow: hidden;

  .swiper-img {
    width: 100%;
  }
}
</style>
