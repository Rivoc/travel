<template>
  <div class="wrapper">
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom"
          v-for="(item) of recommendList"
          :key="item.id">
        <div class="img-wrapper">
          <img class="item-img"
               :src=item.imgURL>
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgURL: 'http://img1.qunarzz.com/sight/source/1505/fb/302620ed8350f8.jpg_r_640x214_25a07cb4.jpg',
        title: '长沙必打卡',
        desc: '到了长沙，一定要到这些地方走走'
      },
      {
        id: '0002',
        imgURL: 'http://img1.qunarzz.com/sight/source/1505/fb/302620ed8350f8.jpg_r_640x214_25a07cb4.jpg',
        title: '长沙必打卡',
        desc: '到了长沙，一定要到这些地方走走'
      },
      {
        id: '0003',
        imgURL: 'http://img1.qunarzz.com/sight/source/1505/fb/302620ed8350f8.jpg_r_640x214_25a07cb4.jpg',
        title: '长沙必打卡',
        desc: '到了长沙，一定要到这些地方走走'
      }

      ]
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/mixins.styl';

.title {
  background: #f5f5f5;
  font-size: 0.14rem;
  line-height: 0.4rem;
  padding-left: 0.13rem;
  font-weight: bold;
}

.item {
  height: 3.43rem;

  .img-wrapper {
    height: 0;
    padding-bottom: 38.461%;
    overflow: hidden;

    .item-img {
      width: 100%;
    }
  }

  .item-info {
    padding: 0.07rem 0.8rem 0.1rem 0.1rem;

    .item-title {
      font-size: 0.14rem;
      margin-bottom: 0.1rem;
      ellipsis();
      min-width: 0;
    }

    .item-desc {
      font-size: 0.12rem;
      ellipsis();
      min-width: 0;
    }
  }
}
</style>
