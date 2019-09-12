<template>
  <div>
    <div class="search">
      <input class="input-search"
             type="text"
             placeholder="请输入城市名或拼音"
             v-model="keyword">
    </div>
    <div class="search-content"
         ref="wrapper"
         v-show="hasKeyWord">
      <ul>
        <li class="search-item border-bottom"
            v-for="item of list"
            :key=item.id
            @click="handleHotCityClick(item.name)">
          {{item.name}}</li>
        <li class="search-item border-bottom"
            v-show="hasNodata">没有找到匹配数据</li>
      </ul>
    </div>
  </div>
</template>
<script>
import Bscroll from 'better-scroll'
export default {
  name: 'HomeSearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  computed: {
    hasNodata () {
      return !this.list.length
    },
    hasKeyWord () {
      return this.keyword
    }
  },
  methods: {
    handleHotCityClick (city) {
      this.$store.commit('cityChange', city)
      this.$router.push('/')
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper, { click: true })
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) { // 搜索之后删掉关键词，清掉结果列表
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  }
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

.search-content {
  position: absolute;
  z-index: 1;
  top: 0.72rem;
  left: 0;
  right: 0;
  bottom: 0;
  background: #fff;
  font-size: 0.14rem;

  .search-item {
    line-height: 0.28rem;
    padding-left: 0.2rem;
  }
}
</style>
