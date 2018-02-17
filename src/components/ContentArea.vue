<template>
  <div class="content-area">
    <div class="overview-container">
      <div class="overview">
        <carousel-bar></carousel-bar>
        <star-board></star-board>
        <star-product-list></star-product-list>
      </div>
    </div>
    <div class="detail-container">
      <div class="detail">
        <mi-gallery v-for="(dataList, idx) in wholeDataList"
                    :dataList="dataList" :key="idx"></mi-gallery>
      </div>
    </div>
  </div>
</template>

<script>
import CarouselBar from './ContentAreaComp/CarouselBar';
import StarBoard from './ContentAreaComp/StarBoard';
import StarProductList from './ContentAreaComp/StarProductList';
import MiGallery from './ContentAreaComp/MiGallery';

const leftItem1 = require('../assets/left-item1.png');
const leftItem2 = require('../assets/left-item2.png');
const leftItem3 = require('../assets/left-item3.png');
const starProduct150 = require('../assets/star_product150.png');
const starProduct80 = require('../assets/star_product80.png');

export default {
  name: 'content-area',
  components: {
    CarouselBar,
    StarBoard,
    StarProductList,
    MiGallery,
  },
  data() {
    return {
      wholeDataList: [
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
    };
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
