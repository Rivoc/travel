<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page,index) of pages"
                    :key="index">
        <div class="
                    icon"
             v-for="item of page"
             :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content"
                 :src="item.imgURL">
          </div>
          <p class="icon-desc">{{item.imgDesc}}</p>
        </div>
      </swiper-slide>
      <div class="swiper-pagination"
           slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeIcons',
  props: {
    iconList: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination'
      }

    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}

</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl';
@import '~styles/mixins.styl';

.icons >>> .swiper-pagination-bullet-active {
  background: #33bfcb;
}

.icons >>> .swiper-container {
  height: 0;
  padding-bottom: 25.3%;
  background: #fff;
}

.icon {
  position: relative;
  float: left;
  height: 0;
  width: 25%;
  padding-bottom: 10.67%;
  margin-top: 0.1rem;

  .icon-img {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0.25rem;

    .icon-img-content {
      display: block;
      margin: 0 auto;
      height: 100%;
    }
  }

  .icon-desc {
    position: absolute;
    padding: 0 0.45rem;
    width: 100%;
    box-sizing: border-box;
    left: 0;
    bottom: 0;
    line-height: 0.25rem;
    color: $darkTextColor;
    font-size: 0.14rem;
    text-align: center;
    ellipsis();
  }
}
</style>
