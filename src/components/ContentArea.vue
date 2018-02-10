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
        <mi-gallery :title="'家电'"></mi-gallery>
      </div>
    </div>
  </div>
</template>

<script>
import CarouselBar from './ContentAreaComp/CarouselBar';
import StarBoard from './ContentAreaComp/StarBoard';
import StarProductList from './ContentAreaComp/StarProductList';
import MiGallery from './ContentAreaComp/MiGallery';

export default {
  name: 'content-area',
  components: {
    CarouselBar,
    StarBoard,
    StarProductList,
    MiGallery,
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
  }
  .detail {
    padding: 60px 0;
  }
</style>
