<!--
走马灯组件
使用方法：
.tg-carousel
  .tg-carousel-item
    .xx-card slot="card"
  .tg-carousel-item
    .xx-card slot="card"
  ...
-->
<template>
  <div class="tg-carousel">
    <div class="left-arrow" :class="currentArrowClass"
         @click="scrollBack"><i class="iconfont">&#xe647;</i></div>
    <div class="right-arrow" :class="currentArrowClass"
         @click="scrollFront"><i class="iconfont">&#xe612;</i></div>
    <slot name="tg-carousel-items" :index="currentIdx"></slot>
    <indicate-points :totalCount="totalCount"
                     :currentCount="currentIdx"
                     :norColor="'rgba(0,0,0, 0.5)'"
                     :hoverColor="'#FF6829'"
                     :selectedColor="'#FF6829'"
                     @switchTo="switchTo"></indicate-points>
  </div>
</template>

<script>
import IndicatePoints from '../CarouselBarComp/IndicatePoints';

export default {
  name: 'tg-carousel',
  props: [
    'hoverState',
    'totalCount',
  ],
  components: {
    IndicatePoints,
  },
  computed: {
    currentArrowClass() {
      const classMap = ['arrow-nor', 'arrow-board-hover'];
      return classMap[this.hoverState];
    },
  },
  methods: {
    switchTo(idx) {
      this.currentIdx = idx;
    },
    scrollFront() {
      if (this.currentIdx === this.totalCount - 1) this.currentIdx = 0;
      else this.currentIdx += 1;
    },
    scrollBack() {
      if (this.currentIdx === 0) this.currentIdx = this.totalCount - 1;
      else this.currentIdx -= 1;
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
  .indicate-points {
    height: 30px;
    position: absolute;
    bottom: 10px;
    left: 50%;
    transform: translateX(-50%);
  }
  .tg-carousel {
    position: relative;
    overflow: hidden;
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
  @font-face {
    font-family: 'iconfont';  /* project id 552033 */
    src: url('//at.alicdn.com/t/font_552033_hptsjrkhmclnb3xr.eot');
    src: url('//at.alicdn.com/t/font_552033_hptsjrkhmclnb3xr.eot?#iefix')
    format('embedded-opentype'),
    url('//at.alicdn.com/t/font_552033_hptsjrkhmclnb3xr.woff') format('woff'),
    url('//at.alicdn.com/t/font_552033_hptsjrkhmclnb3xr.ttf') format('truetype'),
    url('//at.alicdn.com/t/font_552033_hptsjrkhmclnb3xr.svg#iconfont') format('svg');
  }

  .iconfont {
    font-family: "iconfont" !important;
    font-size: 16px;
    font-style: normal;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }
</style>
