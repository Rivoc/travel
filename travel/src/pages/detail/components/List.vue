<template>
  <div>
    <div class="item"
         v-for="(item,index) of list"
         :key="index">
      <div class="item-title border-bottom">
        <span class="item-title-icon">
        </span>
        {{item.title}}
        <div v-if="item.children"
             class="sec-title">
          <detail-list :list="item.children"></detail-list>
        </div>
      </div>
    </div>

  </div>
</template>
<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}
</script>
<style lang="stylus" scoped>
.item-title {
  font-size: 0.16rem;
  font-weight: bold;
  padding: 0.1rem 0rem 0.05rem 0.05rem;

  .item-title-icon {
    display: inline-block;
    width: 0.35rem;
    height: 0.35rem;
    background: url('https://s.qunarzz.com/piao/image/touch/sight/detail.png') 0 -0.45rem no-repeat;
    margin-right: 0.1rem;
    background-size: 0.4rem 3rem;
    vertical-align: middle;
  }

  .sec-title {
    padding: 0 0.2rem;
  }
}
</style>
