<template>
  <div>
    <div class="banner"
         @click="handleBannerClick">
      <img src="//img1.qunarzz.com/sight/p0/1804/1a/1a48cc20b0d6ed44a3.img.jpg_600x330_3f524da7.jpg"
           alt=""
           class="banner-img">
      <div class="banner-info">
        <div class="banner-number">
          <span class="iconfont">&#xe674;</span>
          8</div>
        <div class="banner-title">奥林匹克塔</div>
      </div>
    </div>
    <common-gallery :imgs="imgs"
                    v-if="showGallery"
                    @close="handelClose"></common-gallery>
  </div>
</template>
<script>
import CommonGallery from 'common/gallery/Gallery'
export default {
  name: 'DetailBanner',
  data () {
    return {
      showGallery: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1804/1a/1a48cc20b0d6ed44a3.img.jpg_350x240_8b1488b0.jpg', 'http://img1.qunarzz.com/sight/p0/1804/cf/cfab40f6cd9d80f1a3.img.jpg_350x240_57952850.jpg']
    }
  },
  components: {
    CommonGallery
  },
  methods: {
    handleBannerClick () {
      this.showGallery = true
      console.log('打开')
    },
    handelClose () {
      this.showGallery = false
      console.log('关闭')
    }
  }
}
</script>
<style lang="stylus" scoped>
.banner {
  position: relative;
  height: 0;
  padding-bottom: 55%;
  overflow: hidden;

  .banner-img {
    width: 100%;
  }

  .banner-info {
    position: absolute;
    padding-left: 0.1rem;
    bottom: 0.2rem;
    color: #fff;

    .banner-title {
      font-size: 0.18rem;
    }

    .banner-number {
      width: 0.6rem;
      line-height: 0.2rem;
      font-size: 0.12rem;
      border-radius: 0.2rem;
      background: rgba(0, 0, 0, 0.7);
      margin-bottom: 0.05rem;
      text-align: center;
    }
  }
}
</style>
