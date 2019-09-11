<template>
  <ul class="list">
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
  </ul>
</template>
<script>
export default {
  name: 'CityAlphabet'
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
  top: 1.5rem;
  right: 0;
  bottom: 0;
  color: $bgColor;
  font-size: 0.18rem;
  width: 0.3rem;

  .item {
    margin-bottom: 0.1rem;
  }
}
</style>
