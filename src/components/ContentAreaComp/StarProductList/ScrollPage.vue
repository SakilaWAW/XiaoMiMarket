<template>
  <div class="scroll-page">
    <ul class="container" :style="{width: ulWidth + 'px'}">
      <li class="star-item" v-for="(item, index) in itemList" :key="index">

      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'scroll-page',
  props: ['itemList'],
  computed: {
    ulWidth() {
      return (234 * this.itemList.length) + (17.5 * (this.itemList.length - 1));
    },
  },
};
</script>

<style lang="scss" scoped>
  .scroll-page {
    width: 100%;
    height: 340px;
    border: 1px solid red;
    overflow: hidden;
    display: flex;
    justify-content: space-between;
    font-size: 0;
  }
  .star-item {
    font-size: 16px;
    display: inline-block;
    width: 234px;
    height: 100%;
    background: red;
  }
</style>
