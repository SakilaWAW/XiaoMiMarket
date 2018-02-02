<template>
  <div class="content-area">
    <carousel-bar></carousel-bar>
  </div>
</template>

<script>
import CarouselBar from './ContentAreaComp/CarouselBar';

export default {
  name: 'content-area',
  components: {
    CarouselBar,
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
