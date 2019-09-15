<template>
  <div>
    <div class="banner"
         @click="handleBannerClick">
      <img :src="bannerImg"
           alt=""
           class="banner-img">
      <div class="banner-info">
        <div class="banner-number">
          <span class="iconfont">&#xe674;</span>
          {{this.galleryImgs.length}}</div>
        <div class="banner-title">{{this.sightName}}</div>
      </div>
    </div>
    <fade-animation>
      <common-gallery :imgs="galleryImgs"
                      v-if="showGallery"
                      @close="handelClose"></common-gallery>
    </fade-animation>
  </div>
</template>
<script>
import CommonGallery from 'common/gallery/Gallery'
import FadeAnimation from 'common/fade/fadeAnimation'
export default {
  name: 'DetailBanner',
  props: {
    bannerImg: String,
    sightName: String,
    galleryImgs: Array

  },
  data () {
    return {
      showGallery: false
      // imgs: ['http://img1.qunarzz.com/sight/p0/1804/1a/1a48cc20b0d6ed44a3.img.jpg_350x240_8b1488b0.jpg', 'http://img1.qunarzz.com/sight/p0/1804/cf/cfab40f6cd9d80f1a3.img.jpg_350x240_57952850.jpg']
    }
  },
  components: {
    CommonGallery,
    FadeAnimation
  },
  methods: {
    handleBannerClick () {
      this.showGallery = true
    },
    handelClose () {
      this.showGallery = false
      window.scrollTo(0, 0)
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
