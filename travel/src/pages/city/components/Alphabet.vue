<template>
  <ul class="list">
    <li class="item"
        v-for="key of letters"
        :key="key"
        :ref="key"
        @click="handleClick"
        @touchstart="handleTouchStart"
        @touchmove="handleTouchMove"
        @touchend="handleTouchEnd">{{key}}</li>
  </ul>
</template>
<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  data () {
    return {
      touchStatus: false,
      startY: 0,
      canRun: true
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  computed: {
    letters () {
      const letters = []
      if (this.cities) {
        for (let i in this.cities) {
          letters.push(i)
        }
        return letters
      }
    }
  },
  methods: {
    handleClick (e) {
      this.bus.$emit('childChange', e.target.innerText)
    },
    handleTouchStart () {
      this.touchStatus = true
    },
    handleTouchMove (e) {
      if (this.touchStatus) {
        if (!this.canRun) {
          return
        }
        this.canRun = false
        this.timer = setTimeout(() => {
          const touchY = e.touches[0].clientY
          const letterHeight = 1 * getComputedStyle(this.$refs['A'][0]).marginBottom.slice(0, -2) + 1 * getComputedStyle(this.$refs['A'][0]).height.slice(0, -2)
          const index = Math.floor((touchY - this.startY) / letterHeight)
          if (index >= 0 && index < this.letters.length) {
            this.bus.$emit('childChange', this.letters[index])
          }
          this.canRun = true
        }, 16)
      }
    },
    handleTouchEnd () {
      this.touchStatus = false
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl';
@import '~styles/mixins.styl';

.list {
  position: absolute;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  top: 0;
  right: 0;
  bottom: 0;
  width: 0.3rem;
  color: $bgColor;
}

.item {
  margin-bottom: 0.05rem;
  font-size: 0.18rem;
}
</style>
