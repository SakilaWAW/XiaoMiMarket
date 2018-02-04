<template>
  <div class="content-area">
    <carousel-bar></carousel-bar>
    <star-board></star-board>
  </div>
</template>

<script>
import CarouselBar from './ContentAreaComp/CarouselBar';
import StarBoard from './ContentAreaComp/StarBoard';

export default {
  name: 'content-area',
  components: {
    CarouselBar,
    StarBoard,
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/css/global";

.content-area {
  width: $site-content-width;
  margin: 0 auto;
}
</style>
