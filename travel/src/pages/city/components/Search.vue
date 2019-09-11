<template>
  <div class="search">
    <input class="input-search"
           type="text"
           placeholder="请输入城市名">
  </div>
</template>
<script>
export default {
  name: 'HomeSearch'
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.search {
  padding: 0.1rem;
  padding-top: 0;
  background: $bgColor;

  height, .input-search {
    width: 100%;
    padding: 0 0.03rem;
    box-sizing: border-box;
    font-size: 0.14rem;
    border-radius: 0.05rem;
    color: #666;
  }
}
</style>
