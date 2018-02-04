<template>
  <div class="carousel-bar">
    <carousel-l-list></carousel-l-list>
    <div class="left-arrow" @click="switchBack"><i class="iconfont">&#xe647;</i></div>
    <div class="right-arrow" @click="switchFront"><i class="iconfont">&#xe612;</i></div>
    <indicate-points :total-count="images.length" :currentCount=currentIndex
                     @switchTo="switchTo"></indicate-points>
    <transition-group tag="div" name="carousel-opa">
      <div class="carousel-image-container" v-show="currentIndex===index"
           v-for="(image, index) in images" :key="index"
           @mouseenter="manualScroll" @mouseleave="autoScroll">
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
      switchHandle: 0,
    };
  },
  methods: {
    switchFront() {
      if (this.currentIndex === this.images.length - 1) this.currentIndex = 0;
      else this.currentIndex += 1;
    },
    switchBack() {
      if (this.currentIndex === 0) this.currentIndex = this.images.length - 1;
      else this.currentIndex -= 1;
    },
    switchTo(idx) {
      this.currentIndex = idx;
    },
    autoScroll() {
      this.switchHandle = setInterval(this.switchFront, 4000);
    },
    manualScroll() {
      clearInterval(this.switchHandle);
    },
  },
  mounted() {
    this.autoScroll();
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
    color: rgba(255,255,255,0.5);
    z-index: 1;
    top: 50%;
    transform: translateY(-50%);
  }
  .left-arrow:hover, .right-arrow:hover {
    background: rgba(0,0,0,0.2);
    color: white;
    cursor: pointer;
  }
  .left-arrow {
    left: 234px;
  }
  .right-arrow {
    right: 0;
  }
</style>
