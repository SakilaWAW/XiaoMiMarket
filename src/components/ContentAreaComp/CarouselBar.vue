<template>
  <div class="carousel-bar">
    <carousel-l-list></carousel-l-list>
    <div class="left-arrow" @click="scrollBack"><i class="iconfont">&#xe647;</i></div>
    <div class="right-arrow" @click="scrollFront"><i class="iconfont">&#xe612;</i></div>
    <indicate-points></indicate-points>
    <transition-group tag="div" name="carousel-opa">
      <div class="carousel-image-container" v-show="currentIndex===index"
           v-for="(image, index) in images" :key="index">
        <img class="carousel-image" :src="image.url" alt="image.alt">
        <a :href="image.jumpTo"></a>
      </div>
    </transition-group>
  </div>
</template>

<script>
import CarouselLList from './CarouselBarComp/CarouseLList';
import IndicatePoints from './CarouselBarComp/IndicatePoints';

const caroImg1 = require('../../assets/caroimg1.png');
const caroImg2 = require('../../assets/caroimg2.png');
const caroImg3 = require('../../assets/caroimg3.png');
const caroImg4 = require('../../assets/caroimg4.png');
const caroImg5 = require('../../assets/caroimg5.png');

export default {
  name: 'carousel-bar',
  components: {
    CarouselLList,
    IndicatePoints,
  },
  data() {
    return {
      images: [
        { url: caroImg1, alt: 'img1', jumpTo: 'https://item.mi.com/product/10000080.html' },
        { url: caroImg2, alt: 'img2', jumpTo: 'https://item.mi.com/product/10000080.html' },
        { url: caroImg3, alt: 'img3', jumpTo: 'https://item.mi.com/product/10000080.html' },
        { url: caroImg4, alt: 'img4', jumpTo: 'https://item.mi.com/product/10000080.html' },
        { url: caroImg5, alt: 'img5', jumpTo: 'https://item.mi.com/product/10000080.html' },
      ],
      currentIndex: 0,
    };
  },
  methods: {
    scrollFront() {
      if (this.currentIndex === this.images.length - 1) this.currentIndex = 0;
      else this.currentIndex += 1;
    },
    scrollBack() {
      if (this.currentIndex === 0) this.currentIndex = this.images.length - 1;
      else this.currentIndex -= 1;
    },
  },
};
</script>

<style lang="scss" scoped>
  .carousel-bar {
    position: relative;
    height: 460px;
    width: 100%;
  }
  .carousel-image, .carousel-image-container a {
    height: 100%;
    width: 100%;
    position: absolute;
  }
  // 切换动画
  .carousel-opa-enter, .carousel-opa-leave-to{
    opacity: 0;
  }
  .carousel-opa-enter-active, .carousel-opa-leave-active {
    transition: opacity .5s;
  }
  .carousel-opa-enter-to, .carousel-opa-leave {
    opacity: 1;
  }
  .carousel-bar .iconfont {
    font-size: 40px;
  }
  .left-arrow, .right-arrow {
    width: 41px;
    height: 69px;
    line-height: 69px;
    text-align: center;
    position: absolute;
    z-index: 1;
    top: 50%;
    transform: translateY(-50%);
  }
  .left-arrow:hover, .right-arrow:hover {
    background: rgba(0,0,0,0.2);
    cursor: pointer;
  }
  .left-arrow {
    left: 234px;
  }
  .right-arrow {
    right: 0;
  }
</style>
