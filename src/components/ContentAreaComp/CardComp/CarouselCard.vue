<template>
  <div class="carousel-card hover-shadow" :style="{'border-top-color': mainColor}"
       @mouseenter="hoverState = 1" @mouseleave="hoverState = 0">
    <span class="card-title" :style="{color: mainColor}">{{ item.title }}</span>
    <tg-carousel :hoverState="hoverState"
                 :caroItems="item.items"
                 :specItem="item.spec"></tg-carousel>
  </div>
</template>

<script>
import TgCarousel from '../CommonComp/TgCarousel';

export default {
  name: 'carousel-card',
  props: [
    'item',
    'index',
  ],
  components: {
    TgCarousel,
  },
  data() {
    return {
      hoverState: 0, // 0 为未hover 1为hover到board
    };
  },
  computed: {
    mainColor() {
      const colors = ['orange', 'lightgreen', 'indianred', 'deepskyblue'];
      return colors[this.index];
    },
  },
};
</script>

<style lang="scss" scoped>
  .carousel-card {
    border-top: 1px solid white;
    background: white;
    box-sizing: border-box;
    height: 100%;
    width: 100%;
    text-align: center;
  }
  .card-title {
    font-size: 16px;
    display: block;
    margin-top: 40px;
    margin-bottom: 10px;
  }
  .tg-carousel {
    height: 340px;
    width: 100%;
  }
</style>
