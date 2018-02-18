<template>
  <div class="scroll-board">
    <div class="title">
      <span class="title-txt">{{ title }}</span>
      <left-right-selector :totalPage="maxPage" :currentPage="currentPage"
                           @scrollFront="scrollFront" @scrollBack="scrollBack">
      </left-right-selector>
    </div>
    <slot name="scrollPage" :currentPage="currentPage"></slot>
  </div>
</template>

<script>
import LeftRightSelector from './StarProductList/LeftRightSelector';

export default {
  name: 'scroll-board',
  mounted() {
    this.resetScrollTimer();
  },
  props: [
    'title',
    'maxPage',
    'isScroll',
  ],
  components: {
    LeftRightSelector,
  },
  data() {
    return {
      handler: 0,
      currentPage: 0,
    };
  },
  methods: {
    scroll() {
      this.currentPage = this.currentPage === this.maxPage - 1 ? 0 : this.currentPage + 1;
    },
    scrollFront() {
      this.currentPage += 1;
      this.resetScrollTimer();
    },
    scrollBack() {
      this.currentPage -= 1;
      this.resetScrollTimer();
    },
    resetScrollTimer() {
      window.clearInterval(this.handler);
      if (this.isScroll) {
        this.handler = window.setInterval(() => {
          this.scroll();
        }, 4000);
      }
    },
  },
};
</script>

<style scoped>
  .scroll-board .title{
    position: relative;
    margin-top: 35px;
    width: 100%;
    height: 58px;
  }
  .title-txt {
    font-size: 22px;
    line-height: 58px;
  }
</style>
