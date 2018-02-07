<template>
  <div class="star-product-list">
    <div class="title">
      <span class="title-txt">小米明星单品</span>
      <left-right-selector :totalPage="maxPage" :currentPage="currentPage"
                           @scrollFront="currentPage+=1" @scrollBack="currentPage-=1">
      </left-right-selector>
    </div>
    <scroll-page :itemList="itemList"></scroll-page>
  </div>
</template>

<script>
import LeftRightSelector from './StarProductList/LeftRightSelector';
import ScrollPage from './StarProductList/ScrollPage';

const starProductImg = require('../../assets/star_product.png');

export default {
  name: 'star-product-list',
  components: {
    LeftRightSelector,
    ScrollPage,
  },
  data() {
    return {
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
      ],
    };
  },
  computed: {
    maxPage() {
      return Math.ceil(this.itemList.length / 5);
    },
  },
};
</script>

<style scoped>
  .star-product-list {
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
