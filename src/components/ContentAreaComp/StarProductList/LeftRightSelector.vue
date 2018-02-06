<template>
  <div class="left-right-selector">
    <div class="left-btn iconfont" :class="{unclickable: isStart}"
         @click="scrollBack">&#xe647;</div>
    <div class="right-btn iconfont" :class="{unclickable: isEnd}"
         @click="scrollFront">&#xe612;</div>
  </div>
</template>

<script>
export default {
  name: 'left-right-selector',
  props: [
    'totalPage',
    'currentPage',
  ],
  computed: {
    isStart() {
      return this.currentPage === 0;
    },
    isEnd() {
      return this.currentPage === this.totalPage - 1;
    },
  },
  methods: {
    scrollFront() {
      if (!this.isEnd) this.$emit('scrollFront');
    },
    scrollBack() {
      if (!this.isStart) this.$emit('scrollBack');
    },
  },
};
</script>

<style lang='scss' scoped>
  @import '../../../assets/css/global.scss';
  .left-right-selector {
    position: absolute;
    bottom: 10px;
    right: 0;
    height: 25px;
    width: 70px;
    box-sizing: border-box;
    border: 1px solid $shadow-grey;
    font-size: 0;
  }
  .left-btn, .right-btn {
    color: $dark-dark-grey;
    box-sizing: border-box;
    height: 100%;
    width: 50%;
    line-height: 25px;
    text-align: center;
    display: inline-block;
    font-size: 14px;
    font-weight: bold;
  }
  .left-btn {
    border-right: 1px solid $shadow-grey;
  }
  .left-btn:hover, .right-btn:hover {
    color: $mi-orange;
    cursor: pointer;
  }
  .left-right-selector .unclickable:hover, .left-right-selector .unclickable {
    cursor: auto;
    color: $shadow-grey;
  }
</style>
