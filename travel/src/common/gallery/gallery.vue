<template>
  <div class="container"
       @click="handleSwiperClick">
    <div class="
       wrapper">
      <swiper :options="swiperOptions">
        <swiper-slide v-for="(item,index) in imgs"
                      :key="index">
          <img :src="
                      item"
               class="swiper-img">
        </swiper-slide>
        <div class="swiper-pagination"
             slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>
<script>
export default {
  name: 'CommonGallery',
  props: {
    imgs: {
      type: Array,
      default () {

      }
    }
  },
  data () {
    return {
      swiperOptions: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observeParents: true,
        observer: true
      }
    }
  },
  methods: {
    handleSwiperClick () {
      this.$emit('close')
    }
  }

}
</script>
<style lang="stylus" scoped>
.container >>> .swiper-container {
  overflow: inherit;
}

.container {
  position: fixed;
  z-index: 2;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: #000;
  display: flex;
  align-items: center;

  .wrapper {
    width: 100%;
    height: 0;
    padding-bottom: 68.571%;
    background: #fff;

    .swiper-img {
      width: 100%;
    }

    .swiper-pagination {
      position: absolute;
      color: #fff;
      bottom: -0.5rem;
    }
  }
}
</style>
