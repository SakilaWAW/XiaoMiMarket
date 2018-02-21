<template>
  <div class="carousel-card hover-shadow" :style="{'border-top-color': mainColor}"
       @mouseenter="hoverState = 1" @mouseleave="hoverState = 0">
    <span class="card-title" :style="{color: mainColor}">{{ item.title }}</span>
    <tg-carousel :hoverState="hoverState" :totalCount="totalPagesInCarousel">
      <div class="tg-carousel-item" slot="tg-carousel-items" slot-scope="props"
           :style="{width: scrollerWidth + 'px', 'margin-left': -(props.index * width) + 'px'}">
        <carousel-nor-page-card v-for="(page,index) in item.items" :key="index"
                                :page="page"
                                :width="width"
                                height="340"></carousel-nor-page-card>
        <carousel-spe-page-card :page="item.spec"
                                :width="width"
                                :btnColor="mainColor"
                                height="340"></carousel-spe-page-card>
      </div>
    </tg-carousel>
  </div>
</template>

<script>
import TgCarousel from '../CommonComp/TgCarousel';
import CarouselNorPageCard from '../CardComp/CarouselNorPageCard';
import CarouselSpePageCard from '../CardComp/CarouselSpePageCard';


export default {
  name: 'carousel-card',
  props: [
    'item',
    'index',
    'width',
    'height',
  ],
  components: {
    TgCarousel,
    CarouselNorPageCard,
    CarouselSpePageCard,
  },
  data() {
    return {
      hoverState: 0, // 0 为未hover 1为hover到board
    };
  },
  computed: {
    mainColor() {
      const colors = ['orange', 'darkseagreen', 'indianred', 'deepskyblue'];
      return colors[this.index];
    },
    totalPagesInCarousel() {
      return this.item.items.length + 1;// items+结尾总结页
    },
    scrollerWidth() {
      return this.totalPagesInCarousel * this.width;
    },
  },
};
</script>

<style lang="scss" scoped>
  .carousel-nor-page-card, .carousel-spe-page-card {
    display: inline-block;
    font-size: 0;
    vertical-align: top;
  }
  .carousel-card {
    border-top: 1px solid white;
    background: white;
    box-sizing: border-box;
    height: 100%;
    width: 100%;
    text-align: center;
  }
  .tg-carousel-item {
    transition: margin-left .3s ease-in-out;
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
