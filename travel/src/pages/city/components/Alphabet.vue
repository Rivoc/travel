<template>
  <ul class="list">
    <li class="item"
        v-for="(item,key) of cities"
        :key="key">{{key}}</li>
  </ul>
</template>
<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
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
  color: $bgColor;
  font-size: 0.18rem;
  width: 0.3rem;
  padding-top: 1.5rem;

  .item {
    margin-bottom: 0.05rem;
  }
}
</style>
