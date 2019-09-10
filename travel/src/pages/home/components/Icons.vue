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
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination'
      },
      iconList: [{
        id: '0001',
        imgURL: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        imgDesc: '景点门票'
      }, {
        id: '0002',
        imgURL: 'http://img1.qunarzz.com/piao/fusion/1803/87/20656da0ac042002.png',
        imgDesc: '天门山公园'
      },
      {
        id: '0003',
        imgURL: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
        imgDesc: '长沙必游'
      },
      {
        id: '0004',
        imgURL: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
        imgDesc: '张家界公园'
      }, {
        id: '0005',
        imgURL: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png',
        imgDesc: '演出'
      },
      {
        id: '0006',
        imgURL: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
        imgDesc: '动植物园'
      },
      {
        id: '0007',
        imgURL: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/a40ee278d67000f2a29d2e20f6a029b3.png',
        imgDesc: '自然风光'
      },
      {
        id: '0008',
        imgURL: 'http://img1.qunarzz.com/piao/fusion/1803/b8/c5dcdb58deec2402.png',
        imgDesc: '湘西凤凰'
      },
      {
        id: '0009',
        imgURL: 'http://img1.qunarzz.com/piao/fusion/1803/96/c70f1e85ae4a4f02.png',
        imgDesc: '橘子洲'
      }]
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
