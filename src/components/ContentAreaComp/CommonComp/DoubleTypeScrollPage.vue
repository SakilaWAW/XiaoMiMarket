<template>
  <div class="double-type-scroll-page" :style="{height: height + 'px'}">
    <ul class="container" :style="{'min-width': ulWidth + 'px','margin-left': leftMargin + 'px'}">
      <li class="star-item" v-for="(item, index) in itemList" :key="index"
          :class="{'clear-margin': !hasMargin(index)}">
        <slot name="card" :item="item" :index="index"></slot>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'double-type-scroll-page',
  props: [
    'itemList', // 普通item
    'specList', // 特殊item
    'currentPage',
    'height',
    'width',
    'itemWidth', // 每个item的宽度
    'itemMargin', // 每个item间的距离
    'numInOnePage', // 每页的item个数
  ],
  computed: {
    ulWidth() {
      return (this.totalLength / this.numInOnePage) * this.width;
    },
    leftMargin() {
      return -(this.width * this.currentPage);
    },
    totalLength() {
      return this.itemList.length + this.specList.length;
    },
  },
  methods: {
    hasMargin(idx) {
      return idx % this.numInOnePage !== 0;
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
  .clear-margin {
    margin-right: 0;
  }
</style>
