<template>
  <div class="header">
    <router-link to="/">
      <div class="header-left">
        <span class="iconfont header-back">&#xe624;</span>
      </div>
    </router-link>
    <h1 class=header-title>城市选择</h1>
  </div>
</template>
<script>
export default {
  name: 'CityHeader'
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl';
@import '~styles/mixins.styl';

.header {
  height: 0.34rem;
  background: $bgColor;
  color: #fff;
  text-align: center;

  .header-left {
    position: absolute;
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
