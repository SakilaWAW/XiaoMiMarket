<template>
  <div class="content-area">
    <div class="overview">
      <carousel-bar></carousel-bar>
      <star-board></star-board>
      <star-product-list></star-product-list>
    </div>
  </div>
</template>

<script>
import CarouselBar from './ContentAreaComp/CarouselBar';
import StarBoard from './ContentAreaComp/StarBoard';
import StarProductList from './ContentAreaComp/StarProductList';

export default {
  name: 'content-area',
  components: {
    CarouselBar,
    StarBoard,
    StarProductList,
  },
};
</script>

<style lang="scss" scoped>
  @import "../assets/css/global";

  .content-area {
    width: 100%;
    background: white;
  }
  .overview {
    width: $site-content-width;
    margin: 0 auto;
  }
</style>
