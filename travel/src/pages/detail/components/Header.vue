<template>
  <div>
    <router-link to="/">
      <div class="header-abs"
           v-show="showAbs"
           ref="absHeader">
        <span class="iconfont">&#xe624;</span>
      </div>
    </router-link>

    <div class="header-fixed"
         v-show="!showAbs"
         :style="opacityStyle">
      <router-link tag="span"
                   to="/"
                   class="iconfont header-back">&#xe624;</router-link>
      <h1 class=header-title>城市选择</h1>
    </div>
  </div>
</template>
<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: 'true',
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      console.log('aa')
      const absHeaderHeight = getComputedStyle(this.$refs.absHeader).height.slice(0, -2)
      const top = document.documentElement.scrollTop
      if (top > absHeaderHeight) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.showAbs = false
        this.opacityStyle = {
          opacity
        }
      } else {
        this.showAbs = true
      }
    }
  },

  activated () {
    window.addEventListener('scroll', this.handleScroll)
    window.scrollTo(0, 0)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl';
@import '~styles/mixins.styl';

.header-abs {
  position: absolute;
  top: 0.08rem;
  left: 0.08rem;
  width: 0.36rem;
  height: 0.36rem;
  line-height: 0.36rem;
  text-align: center;
  color: #fff;
  font-size: 0.18rem;
  border-radius: 50%;
  background: rgba(0, 0, 0, 0.7);
}

.header-fixed {
  position: fixed;
  width: 100%;
  top: 0;
  left: 0;
  height: 0.34rem;
  background: $bgColor;
  color: #fff;
  text-align: center;

  .header-back {
    position: absolute;
    left: 0;
    width: 0.4rem;
    line-height: 0.34rem;
    height: 0.34rem;
    font-size: 0.18rem;
    color: #fff;
  }

  .header-title {
    flex: 1;
    font-size: 0.16rem;
    headerHeight(0.34rem);
  }
}
</style>
