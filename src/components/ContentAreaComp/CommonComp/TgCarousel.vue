<template>
  <div class="tg-carousel">
    <div class="left-arrow" :class="currentArrowClass"><i class="iconfont">&#xe647;</i></div>
    <div class="right-arrow" :class="currentArrowClass"><i class="iconfont">&#xe612;</i></div>
  </div>
</template>

<script>
export default {
  name: 'tg-carousel',
  props: [
    'hoverState',
    'caroItems',
    'specItem',
  ],
  computed: {
    currentArrowClass() {
      const classMap = ['arrow-nor', 'arrow-board-hover'];
      return classMap[this.hoverState];
    },
  },
  data() {
    return {
      currentIdx: 0,
    };
  },
};
</script>

<style lang="scss" scoped>
  @import '../../../assets/css/global';
  .tg-carousel {
    position: relative;
  }
  .left-arrow, .right-arrow {
    top: 30%;
    position: absolute;
    padding: 15px 3px;
    color: white;
  }
  .left-arrow:hover, .right-arrow:hover {
    display: block;
    background: $dark-dark-grey;
    cursor: pointer;
  }
  .arrow-board-hover {
    display: block;
    background: $shadow-grey;
  }
  .arrow-nor {
    display: none;
  }
  .left-arrow i, .right-arrow i {
    font-size: 15px;
  }
  .left-arrow {
    left: 0;
  }
  .right-arrow {
    right: 0;
  }
</style>
