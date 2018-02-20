<template>
  <div class="scroll-page" :style="{height: height + 'px'}">
    <ul class="container" :style="{'min-width': ulWidth + 'px','margin-left': leftMargin + 'px'}">
      <li class="star-item" v-for="(item, index) in itemList" :key="index">
        <slot name="card" :item="item" :index="index"></slot>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'scroll-page',
  props: [
    'itemList',
    'currentPage',
    'height',
  ],
  computed: {
    ulWidth() {
      return (this.itemList.length / 5) * 1240;
    },
    leftMargin() {
      return -(1240 * this.currentPage);
    },
  },
};
</script>

<style lang="scss" scoped>
  .scroll-page {
    width: 100%;
    margin-bottom: 40px;
  }
  .container {
    font-size: 0;
    text-align: center;
    height: 100%;
    transition: margin-left .8s ease-in-out;
  }
  .star-item {
    display: inline-block;
    width: 234px;
    margin-right: 17.5px;
    height: 100%;
  }
  .star-item:nth-child(5n) {
    margin-right: 0;
  }
</style>
