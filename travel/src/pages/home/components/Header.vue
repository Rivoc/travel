<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont">&#xe624;</span>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩主题</div>
    <router-link to="/city">
      <div class="header-right">
        {{this.$store.state.city}}
        <span class="iconfont arrow-icon">&#xe614;</span>
      </div>
    </router-link>
  </div>
</template>
<script>
export default {
  name: 'HomeHeader'
  // props: {
  //   city: String
  // }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.header {
  display: flex;
  justify-content: center;
  align-items: center;
  line-height: 0.44rem;
  background: $bgColor;
  color: #fff;
}

.header-left {
  width: 0.4rem;
  font-size: 0.18rem;
  text-align: center;
}

.header-input {
  flex: 1;
  line-height: 0.3rem;
  padding-left: 0.1rem;
  border-radius: 0.05rem;
  font-size: 0.14rem;
  color: #E4E7EA;
  background: #fff;
}

.header-right {
  width: 0.64rem;
  font-size: 0.14rem;
  text-align: center;
  color: #fff;

  .arrow-icon {
    font-size: 0.12rem;
  }
}
</style>
