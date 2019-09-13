<template>
  <div class="wrapper">
    <div class="title">猜你喜欢</div>
    <ul>
      <router-link tag="li"
                   :to="'/detail/'+item.id"
                   class="item border-bottom"
                   v-for="item of recommendList"
                   :key="item.id">
        <img class="item-img"
             :src=item.imgURL>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeRecommend',
  props: {
    recommendList: Array
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/mixins.styl';

.wrapper {
  margin-top: 0.1rem;
  background: #fff;

  .title {
    line-height: 0.22rem;
    padding: 0.12rem 0.1rem;
    font-size: 0.16rem;
  }

  .item {
    display: flex;
    padding: 0.1rem;
    height: 1rem;
    overflow: hidden;
  }

  .item-img {
    width: 1rem;
    height: 1rem;
  }

  .item-info {
    flex: 1;
    padding-left: 0.11rem;
  }

  .item-title {
    margin-top: 0.13rem;
    font-size: 0.16rem;
    min-width: 0;
    ellipsis();
  }

  .item-desc {
    font-size: 0.12rem;
    margin-top: 0.07rem;
    min-width: 0;
    ellipsis();
  }

  .item-button {
    margin-top: 0.35rem;
    font-size: 0.12rem;
    color: #ff8300;
    background: transparent;
  }
}
</style>
