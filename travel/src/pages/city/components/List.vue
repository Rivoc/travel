<template>
  <div class="list"
       ref="wrapper">
    <div>
      <div class="area">
        <h2 class="title">当前城市</h2>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">长沙</div>
          </div>
        </div>
      </div>
      <div class="area">
        <h2 class="title">热门城市</h2>
        <div class="button-list">
          <div class="button-wrapper"
               v-for="item of hotCities"
               :key="item.id">
            <div class="button">{{item.name}}</div>
          </div>
          <!-- <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div> -->
        </div>
      </div>
      <div class="area"
           v-for="(item,key) of cities"
           :key="key">
        <h2 class="title border-topbottom">{{key}}</h2>
        <div class="item-list">
          <div class="item border-bottom"
               v-for="innerItem of item"
               :key="innerItem.id">
            {{innerItem.name}}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CityList',
  props: {
    cities: Object,
    hotCities: Array
  },
  mounted () {
    console.log(this.$refs.wrapper)
    this.scroll = new Bscroll(this.$refs.wrapper)
  }
}
</script>
<style lang="stylus" scoped>
.border-topbottom {
  &:before {
    color: #e7e7e7;

    &:after {
      color: #e7e7e7;
    }
  }
}

.list {
  position: absolute;
  top: 0.725rem;
  left: 0;
  right: 0;
  bottom: 0;
  background: #f5f5f5;
  overflow: hidden;

  .title {
    font-size: 0.12rem;
    padding: 0.12rem 0.15rem;
  }

  .button-list {
    display: flex;
    flex-wrap: wrap;
    padding: 0.2rem 0.3rem 0 0.3rem;
    background: #fff;

    .button-wrapper {
      width: 2rem;
      border: 1px solid #dedede;
      text-align: center;
      margin-right: 0.2rem;
      margin-bottom: 0.2rem;

      .button {
        font-size: 0.14rem;
        line-height: 0.28rem;
      }
    }

    .button-wrapper:nth-of-type(3n) {
      margin-right: 0;
    }
  }

  .item-list {
    background: #fff;
    line-height: 0.4rem;
    font-size: 0.14rem;

    .item {
      padding-left: 0.15rem;
      padding-right: 0.6rem;
    }
  }
}
</style>
