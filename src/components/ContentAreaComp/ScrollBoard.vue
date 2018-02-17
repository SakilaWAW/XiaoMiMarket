<template>
  <div class="scroll-board">
    <div class="title">
      <span class="title-txt">{{ title }}</span>
      <left-right-selector :totalPage="maxPage" :currentPage="currentPage"
                           @scrollFront="scrollFront" @scrollBack="scrollBack">
      </left-right-selector>
    </div>
    <scroll-page :itemList="itemList" :currentPage="currentPage"></scroll-page>
  </div>
</template>

<script>
import LeftRightSelector from './StarProductList/LeftRightSelector';
import ScrollPage from './StarProductList/ScrollPage';

const starProductImg = require('../../assets/star_product.png');

export default {
  name: 'scroll-board',
  mounted() {
    this.resetScrollTimer();
  },
  props: [
    'title',
  ],
  components: {
    LeftRightSelector,
    ScrollPage,
  },
  data() {
    return {
      handler: 0,
      currentPage: 0,
      itemList: [
        { img: starProductImg, name: '小米手环2', desc: 'OLED显示屏幕，升级记步算法', subDesc: '149元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg, name: '米家扫地机器人', desc: '爱干净，高效完成清扫任务', subDesc: '1699元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg, name: '小米手环2', desc: 'OLED显示屏幕，升级记步算法', subDesc: '149元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg, name: '米家扫地机器人', desc: '爱干净，高效完成清扫任务', subDesc: '1699元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg, name: '小米手环2', desc: 'OLED显示屏幕，升级记步算法', subDesc: '149元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg, name: '米家扫地机器人', desc: '爱干净，高效完成清扫任务', subDesc: '1699元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg, name: '小米手环2', desc: 'OLED显示屏幕，升级记步算法', subDesc: '149元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg, name: '米家扫地机器人', desc: '爱干净，高效完成清扫任务', subDesc: '1699元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg, name: '小米手环2', desc: 'OLED显示屏幕，升级记步算法', subDesc: '149元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg, name: '米家扫地机器人', desc: '爱干净，高效完成清扫任务', subDesc: '1699元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg, name: '米家扫地机器人', desc: '爱干净，高效完成清扫任务', subDesc: '1699元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg, name: '小米手环2', desc: 'OLED显示屏幕，升级记步算法', subDesc: '149元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg, name: '米家扫地机器人', desc: '爱干净，高效完成清扫任务', subDesc: '1699元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg, name: '小米手环2', desc: 'OLED显示屏幕，升级记步算法', subDesc: '149元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg, name: '米家扫地机器人', desc: '爱干净，高效完成清扫任务', subDesc: '1699元', href: 'https://item.mi.com/product/10000070.html' },
      ],
    };
  },
  computed: {
    maxPage() {
      return Math.ceil(this.itemList.length / 5);
    },
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
      this.handler = window.setInterval(() => {
        this.scroll();
      }, 4000);
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
