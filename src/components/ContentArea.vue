<template>
  <div class="content-area">
    <div class="overview-container">
      <div class="overview">
        <carousel-bar></carousel-bar>
        <star-board></star-board>
        <star-product-list></star-product-list>
      </div>
    </div>
    <div class="detail-container">
      <div class="detail">
      </div>
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
  .overview, .detail {
    width: $site-content-width;
    margin: 0 auto;
  }
  .detail-container {
    background: #F5F5F5;
    height: 1000px;
  }
  .shadow-hover:hover {
    cursor: pointer;
    box-shadow: 5px 5px 10px $shadow-color;
    transition: box-shadow .3s ease-in-out;
  }
</style>
