<template>
  <div class="content-area">
    <div class="overview-container">
      <div class="overview">
        <carousel-bar></carousel-bar>
        <star-board></star-board>
        <scroll-board :title="'小米明星单品'"
                      :maxPage="starProductMaxPage"
                      :isScroll="true">
          <scroll-page slot="scrollPage" slot-scope="props"
                       :itemList="starProductItemList"
                       :currentPage="props.currentPage"
                       :height="340">
            <mi-star-product-card slot="card" slot-scope="props"
                     :item="props.item" :index="props.index"></mi-star-product-card>
          </scroll-page>
        </scroll-board>
      </div>
    </div>
    <div class="detail-container">
      <div class="detail">
        <mi-gallery v-for="(dataList, idx) in miGalleryDataList"
                    :dataList="dataList" :key="idx"></mi-gallery>
        <scroll-board :title="'为你推荐'"
                      :maxPage="justForYouMaxPage"
                      :isScroll="false">
          <scroll-page slot="scrollPage" slot-scope="props"
                       :itemList="justForYouItemList"
                       :currentPage="props.currentPage"
                       :height="300">
            <just-for-you-card slot="card" slot-scope="props"
                                  :item="props.item"></just-for-you-card>
          </scroll-page>
        </scroll-board>
        <display-board-in-four :height="415" :title="'热评产品'" :items="hotItemList">
          <hot-item-card slot="card" slot-scope="props" :item="props.item"></hot-item-card>
        </display-board-in-four>
      </div>
    </div>
  </div>
</template>

<script>
import CarouselBar from './ContentAreaComp/CarouselBar';
import StarBoard from './ContentAreaComp/StarBoard';
import ScrollBoard from './ContentAreaComp/ScrollBoard';
import DisplayBoardInFour from './ContentAreaComp/DisplayBoardInFour';
import HotItemCard from './ContentAreaComp/CardComp/HotItemCard';
import ScrollPage from './ContentAreaComp/StarProductList/ScrollPage';
import MiGallery from './ContentAreaComp/MiGallery';
import MiStarProductCard from './ContentAreaComp/CardComp/MiStarProductCard';
import JustForYouCard from './ContentAreaComp/CardComp/JustForYouCard';

const leftItem1 = require('../assets/left-item1.png');
const leftItem2 = require('../assets/left-item2.png');
const leftItem3 = require('../assets/left-item3.png');
const starProduct150 = require('../assets/star_product150.png');
const starProduct80 = require('../assets/star_product80.png');
const starProductImg160 = require('../assets/star_product160.png');
const starProductImg140 = require('../assets/star_product140.png');
const hotItem1 = require('../assets/hot-item1.png');
const hotItem2 = require('../assets/hot-item2.png');
const hotItem3 = require('../assets/hot-item3.png');
const hotItem4 = require('../assets/hot-item4.png');


export default {
  name: 'content-area',
  components: {
    CarouselBar,
    StarBoard,
    ScrollBoard,
    ScrollPage,
    MiStarProductCard,
    JustForYouCard,
    MiGallery,
    DisplayBoardInFour,
    HotItemCard,
  },
  data() {
    return {
      miGalleryDataList: [
        {
          name: '家电',
          types: ['家电', '电视影音', '电脑', '家具'],
          leftBar: [
            { img: leftItem1, href: 'https://www.mi.com/scooter/' },
          ],
          items: [
            {
              nor: [
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', oPrice: '1288元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
              ],
              addOn: { name: '小白摄像机', price: '1399元', img: starProduct80, url: 'https://www.mi.com/yeelight-ceilinglamp/' },
              moreUrl: 'https://www.mi.com/mitv4A/32/',
            },
            {
              nor: [
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
              ],
              addOn: { name: '小米盒子3S', price: '299元', img: starProduct80, url: 'https://www.mi.com/yeelight-ceilinglamp/' },
              moreUrl: 'https://www.mi.com/mitv4A/32/',
            },
            {
              nor: [
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
              ],
              addOn: { name: '多功能转换器', price: '88元', img: starProduct80, url: 'https://www.mi.com/yeelight-ceilinglamp/' },
              moreUrl: 'https://www.mi.com/mitv4A/32/',
            },
            {
              nor: [
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
              ],
              addOn: { name: 'Yeelight LED 吸顶灯', price: '399元', img: starProduct80, url: 'https://www.mi.com/yeelight-ceilinglamp/' },
              moreUrl: 'https://www.mi.com/mitv4A/32/',
            },
          ],
        },
        {
          name: '家电',
          types: ['热门', '出行', '健康', '酷玩', '路由器'],
          leftBar: [
            { img: leftItem1, href: 'https://www.mi.com/scooter/' },
          ],
          items: [
            {
              nor: [
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', oPrice: '1288元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
              ],
              addOn: { name: '小白摄像机', price: '1399元', img: starProduct80, url: 'https://www.mi.com/yeelight-ceilinglamp/' },
              moreUrl: 'https://www.mi.com/mitv4A/32/',
            },
            {
              nor: [
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
              ],
              addOn: { name: '小米盒子3S', price: '299元', img: starProduct80, url: 'https://www.mi.com/yeelight-ceilinglamp/' },
              moreUrl: 'https://www.mi.com/mitv4A/32/',
            },
            {
              nor: [
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
              ],
              addOn: { name: '多功能转换器', price: '88元', img: starProduct80, url: 'https://www.mi.com/yeelight-ceilinglamp/' },
              moreUrl: 'https://www.mi.com/mitv4A/32/',
            },
            {
              nor: [
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
              ],
              addOn: { name: 'Yeelight LED 吸顶灯', price: '399元', img: starProduct80, url: 'https://www.mi.com/yeelight-ceilinglamp/' },
              moreUrl: 'https://www.mi.com/mitv4A/32/',
            },
            {
              nor: [
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
              ],
              addOn: { name: 'Yeelight LED 吸顶灯', price: '399元', img: starProduct80, url: 'https://www.mi.com/yeelight-ceilinglamp/' },
              moreUrl: 'https://www.mi.com/mitv4A/32/',
            },
          ],
        },
        {
          name: '家电',
          types: ['家电', '电视影音', '电脑', '家具'],
          leftBar: [
            { img: leftItem2, href: 'https://www.mi.com/scooter/' },
            { img: leftItem3, href: 'https://www.mi.com/scooter/' },
          ],
          items: [
            {
              nor: [
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', oPrice: '1288元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
              ],
              addOn: { name: '小白摄像机', price: '1399元', img: starProduct80, url: 'https://www.mi.com/yeelight-ceilinglamp/' },
              moreUrl: 'https://www.mi.com/mitv4A/32/',
            },
            {
              nor: [
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
              ],
              addOn: { name: '小米盒子3S', price: '299元', img: starProduct80, url: 'https://www.mi.com/yeelight-ceilinglamp/' },
              moreUrl: 'https://www.mi.com/mitv4A/32/',
            },
            {
              nor: [
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
              ],
              addOn: { name: '多功能转换器', price: '88元', img: starProduct80, url: 'https://www.mi.com/yeelight-ceilinglamp/' },
              moreUrl: 'https://www.mi.com/mitv4A/32/',
            },
            {
              nor: [
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
              ],
              addOn: { name: 'Yeelight LED 吸顶灯', price: '399元', img: starProduct80, url: 'https://www.mi.com/yeelight-ceilinglamp/' },
              moreUrl: 'https://www.mi.com/mitv4A/32/',
            },
          ],
        },
        {
          name: '家电',
          types: ['家电', '电视影音', '电脑', '家具'],
          leftBar: [
            { img: leftItem2, href: 'https://www.mi.com/scooter/' },
            { img: leftItem3, href: 'https://www.mi.com/scooter/' },
          ],
          items: [
            {
              nor: [
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', oPrice: '1288元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
              ],
              addOn: { name: '小白摄像机', price: '1399元', img: starProduct80, url: 'https://www.mi.com/yeelight-ceilinglamp/' },
              moreUrl: 'https://www.mi.com/mitv4A/32/',
            },
            {
              nor: [
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
              ],
              addOn: { name: '小米盒子3S', price: '299元', img: starProduct80, url: 'https://www.mi.com/yeelight-ceilinglamp/' },
              moreUrl: 'https://www.mi.com/mitv4A/32/',
            },
            {
              nor: [
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
              ],
              addOn: { name: '多功能转换器', price: '88元', img: starProduct80, url: 'https://www.mi.com/yeelight-ceilinglamp/' },
              moreUrl: 'https://www.mi.com/mitv4A/32/',
            },
            {
              nor: [
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
              ],
              addOn: { name: 'Yeelight LED 吸顶灯', price: '399元', img: starProduct80, url: 'https://www.mi.com/yeelight-ceilinglamp/' },
              moreUrl: 'https://www.mi.com/mitv4A/32/',
            },
          ],
        },
        {
          name: '家电',
          types: ['家电', '电视影音', '电脑', '家具'],
          leftBar: [
            { img: leftItem2, href: 'https://www.mi.com/scooter/' },
            { img: leftItem3, href: 'https://www.mi.com/scooter/' },
          ],
          items: [
            {
              nor: [
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', oPrice: '1288元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
              ],
              addOn: { name: '小白摄像机', price: '1399元', img: starProduct80, url: 'https://www.mi.com/yeelight-ceilinglamp/' },
              moreUrl: 'https://www.mi.com/mitv4A/32/',
            },
            {
              nor: [
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
              ],
              addOn: { name: '小米盒子3S', price: '299元', img: starProduct80, url: 'https://www.mi.com/yeelight-ceilinglamp/' },
              moreUrl: 'https://www.mi.com/mitv4A/32/',
            },
            {
              nor: [
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
              ],
              addOn: { name: '多功能转换器', price: '88元', img: starProduct80, url: 'https://www.mi.com/yeelight-ceilinglamp/' },
              moreUrl: 'https://www.mi.com/mitv4A/32/',
            },
            {
              nor: [
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
                { url: 'https://www.mi.com/mitv4A/32/', topDesc: '', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，品质优良，电脑刚开机，性能那真的是刚刚的呀！', author: '来自于 李业兴 的评价' },
              ],
              addOn: { name: 'Yeelight LED 吸顶灯', price: '399元', img: starProduct80, url: 'https://www.mi.com/yeelight-ceilinglamp/' },
              moreUrl: 'https://www.mi.com/mitv4A/32/',
            },
          ],
        },
      ],
      starProductItemList: [
        { img: starProductImg160, name: '小米手环2', desc: 'OLED显示屏幕，升级记步算法', subDesc: '149元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg160, name: '米家扫地机器人', desc: '爱干净，高效完成清扫任务', subDesc: '1699元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg160, name: '小米手环2', desc: 'OLED显示屏幕，升级记步算法', subDesc: '149元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg160, name: '米家扫地机器人', desc: '爱干净，高效完成清扫任务', subDesc: '1699元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg160, name: '小米手环2', desc: 'OLED显示屏幕，升级记步算法', subDesc: '149元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg160, name: '米家扫地机器人', desc: '爱干净，高效完成清扫任务', subDesc: '1699元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg160, name: '小米手环2', desc: 'OLED显示屏幕，升级记步算法', subDesc: '149元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg160, name: '米家扫地机器人', desc: '爱干净，高效完成清扫任务', subDesc: '1699元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg160, name: '小米手环2', desc: 'OLED显示屏幕，升级记步算法', subDesc: '149元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg160, name: '米家扫地机器人', desc: '爱干净，高效完成清扫任务', subDesc: '1699元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg160, name: '米家扫地机器人', desc: '爱干净，高效完成清扫任务', subDesc: '1699元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg160, name: '小米手环2', desc: 'OLED显示屏幕，升级记步算法', subDesc: '149元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg160, name: '米家扫地机器人', desc: '爱干净，高效完成清扫任务', subDesc: '1699元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg160, name: '小米手环2', desc: 'OLED显示屏幕，升级记步算法', subDesc: '149元', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg160, name: '米家扫地机器人', desc: '爱干净，高效完成清扫任务', subDesc: '1699元', href: 'https://item.mi.com/product/10000070.html' },
      ],
      justForYouItemList: [
        { img: starProductImg140, name: '红米Note 5A增强版 全网通 6GB大内存', price: '3999元', subDesc: '9192人好评', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg140, name: '红米Note 5A增强版 全网通 6GB大内存', price: '3999元', subDesc: '9192人好评', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg140, name: '红米Note 5A增强版 全网通 6GB大内存', price: '3999元', subDesc: '9192人好评', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg140, name: '红米Note 5A增强版 全网通 6GB大内存', price: '3999元', subDesc: '9192人好评', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg140, name: '红米Note 5A增强版 全网通 6GB大内存', price: '3999元', subDesc: '9192人好评', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg140, name: '红米Note 5A增强版 全网通 6GB大内存', price: '3999元', subDesc: '9192人好评', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg140, name: '红米Note 5A增强版 全网通 6GB大内存', price: '3999元', subDesc: '9192人好评', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg140, name: '红米Note 5A增强版 全网通 6GB大内存', price: '3999元', subDesc: '9192人好评', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg140, name: '红米Note 5A增强版 全网通 6GB大内存', price: '3999元', subDesc: '9192人好评', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg140, name: '红米Note 5A增强版 全网通 6GB大内存', price: '3999元', subDesc: '9192人好评', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg140, name: '红米Note 5A增强版 全网通 6GB大内存', price: '3999元', subDesc: '9192人好评', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg140, name: '红米Note 5A增强版 全网通 6GB大内存', price: '3999元', subDesc: '9192人好评', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg140, name: '红米Note 5A增强版 全网通 6GB大内存', price: '3999元', subDesc: '9192人好评', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg140, name: '红米Note 5A增强版 全网通 6GB大内存', price: '3999元', subDesc: '9192人好评', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg140, name: '红米Note 5A增强版 全网通 6GB大内存', price: '3999元', subDesc: '9192人好评', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg140, name: '红米Note 5A增强版 全网通 6GB大内存', price: '3999元', subDesc: '9192人好评', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg140, name: '红米Note 5A增强版 全网通 6GB大内存', price: '3999元', subDesc: '9192人好评', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg140, name: '红米Note 5A增强版 全网通 6GB大内存', price: '3999元', subDesc: '9192人好评', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg140, name: '红米Note 5A增强版 全网通 6GB大内存', price: '3999元', subDesc: '9192人好评', href: 'https://item.mi.com/product/10000070.html' },
        { img: starProductImg140, name: '红米Note 5A增强版 全网通 6GB大内存', price: '3999元', subDesc: '9192人好评', href: 'https://item.mi.com/product/10000070.html' },
      ],
      hotItemList: [
        { img: hotItem1, comment: '东西真心不错，用过最好用的插线板，做工外观没得挑剔，3个USB接口很实用，充电快，建议不包邮的应该在商品详情页中具体标注出来，以免产生误解。', author: '来自于 yinyin19891117 的评价', price: '1239元', name: '米家小白只能照相机', href: 'https://www.mi.com/powerstrip/' },
        { img: hotItem2, comment: '东西真心不错，用过最好用的插线板，做工外观没得挑剔，3个USB接口很实用，充电快，建议不包邮的应该在商品详情页中具体标注出来，以免产生误解。', author: '来自于 yinyin19891117 的评价', price: '1239元', name: '米家小白只能照相机', href: 'https://www.mi.com/powerstrip/' },
        { img: hotItem3, comment: '东西真心不错，用过最好用的插线板，做工外观没得挑剔，3个USB接口很实用，充电快，建议不包邮的应该在商品详情页中具体标注出来，以免产生误解。', author: '来自于 yinyin19891117 的评价', price: '1239元', name: '米家小白只能照相机', href: 'https://www.mi.com/powerstrip/' },
        { img: hotItem4, comment: '东西真心不错，用过最好用的插线板，做工外观没得挑剔，3个USB接口很实用，充电快，建议不包邮的应该在商品详情页中具体标注出来，以免产生误解。', author: '来自于 yinyin19891117 的评价', price: '1239元', name: '米家小白只能照相机', href: 'https://www.mi.com/powerstrip/' },
      ],
    };
  },
  computed: {
    starProductMaxPage() {
      return Math.ceil(this.starProductItemList.length / 5);
    },
    justForYouMaxPage() {
      return Math.ceil(this.justForYouItemList.length / 5);
    },
  },
};
</script>

<style lang="scss" scoped>
  @import "../assets/css/global";

  .content-area {
    width: 100%;
    background: white;
  }
  .overview, .detail {
    width: $site-content-width;
    margin: 0 auto;
  }
  .detail-container {
    background: #F5F5F5;
  }
  .detail {
    padding: 60px 0;
  }
  .mi-gallery {
    margin-bottom: 70px;
  }
</style>
