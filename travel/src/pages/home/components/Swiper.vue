<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item of swiperList"
                    :key="item.id">
        <img :src="item.imgURL"
             alt="图片1"
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
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgURL: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20199/6732b10fa1a3b08b883e4aebd2e37f44.jpg_750x200_83dd47e1.jpg'
      },
      {
        id: '0002',
        imgURL: 'http://img1.qunarzz.com/piao/fusion/1706/b8/a8e8ff02b094c802.jpg_750x200_ddaec8e5.jpg'
      },
      {
        id: '0003',
        imgURL: 'http://img1.qunarzz.com/piao/fusion/1706/b9/6b91b49794f46402.jpg_750x200_d7f254e2.jpg'
      }]
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
