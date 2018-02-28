<template>
  <div class="display-board-in-four">
    <div class="title">
      {{ title }}
      <slot name="sub-title"></slot>
    </div>
    <ul class="content" :style="{height: height + 'px'}">
      <li class="card-container" v-for="(item, idx) in items" :key="idx"
          :class="{'clear-right-margin': !hasRightMargin(idx)}">
        <slot name="card" :item="item" :idx="idx"></slot>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'display-board-in-four',
  props: [
    'title',
    'items',
    'height',
  ],
  methods: {
    hasRightMargin(idx) {
      return idx !== this.items.length - 1;
    },
  },
};
</script>

<style lang="scss" scoped>
  .title {
    font-size: 22px;
    line-height: 58px;
    position: relative;
  }
  .content {
    width: 100%;
    font-size: 0;
  }
  .card-container {
    display: inline-block;
    width: 295px;
    height: 100%;
    margin-right: 20px;
  }
  .clear-right-margin {
    margin-right: 0;
  }
</style>
