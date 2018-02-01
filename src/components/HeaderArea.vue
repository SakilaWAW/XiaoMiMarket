<template>
  <div id="header-area">
    <div id="header-container">
      <div id="site-header">
        <ul id="left-header">
          <li class="split-right"><a href="">小米商城</a></li>
          <li class="split-right"><a href="">MIUI</a></li>
          <li class="split-right"><a href="">IoT</a></li>
          <li class="split-right"><a href="">云服务</a></li>
          <li class="split-right"><a href="">水滴</a></li>
          <li class="split-right"><a href="">金融</a></li>
          <li class="split-right"><a href="">有品</a></li>
          <li><a href="">Select Region</a></li>
        </ul>
        <ul id="right-header">
          <li class="split-right"><a href="">登陆</a></li>
          <li class="split-right"><a href="">注册</a></li>
          <li><a href="">消息通知</a></li>
          <li id="cart">
            <a id="cart-link" @mouseenter="showPopBlock=true" :class="{'cart-hover': showPopBlock}"
               @mouseleave="showPopBlock=false" href=""><i class="iconfont">&#xe60f;</i>购物车(0)</a>
            <transition name="toggle">
              <div id="pop-cart-block" @mouseenter="showPopBlock=true"
                   @mouseleave="showPopBlock=false" v-show="showPopBlock">
                购物车中还没有商品，赶紧选购吧！
              </div>
            </transition>
          </li>
        </ul>
      </div>
    </div>
    <div class="site-nav-container">
      <div class="site-nav">
        <div class="site-logo">
          <a class="logo-container" href="https://www.baidu.com">
            <img class="mi-logo" src="../assets/mi_logo.png" alt="">
          </a>
        </div>
        <ul class="nav-list">
          <li class="sub-gg"><a href=""></a></li>
          <li v-for="(menu, index) in navListMenu" :key="index"
              @mouseenter="hoverNavList(menu.name)" @mouseleave="showExpandMenu=false">
            <span>
              {{ menu.name }}
            </span>
          </li>
        </ul>
        <search-box :initTags="searchInitTags"></search-box>
      </div>
      <transition name="exp-toggle">
        <expand-menu v-show="showExpandMenu" :items="expandMenuCurContent"
                     @show="showExpandMenu=true" @disappear="showExpandMenu=false"></expand-menu>
      </transition>
    </div>
  </div>
</template>

<script>
import SearchBox from './HeaderAreaComp/SearchBox';
import ExpandMenu from './HeaderAreaComp/ExpandMenu';

const phonePic = require('../assets/phone.png');

const expandMenuContent = {
  小米手机: [
    { topDes: '新品', img: phonePic, name: '红米Note3', bottomDes: '1233元起', hrefPostfix: 'mi5x' },
    { topDes: '新品', img: phonePic, name: '小米7', bottomDes: '2013元起', hrefPostfix: 'mi5x' },
    { topDes: '爆款', img: phonePic, name: '红米4', bottomDes: '1399元起', hrefPostfix: 'mi5x' },
    { topDes: '全面屏', img: phonePic, name: '小米Mix2', bottomDes: '3999元起', hrefPostfix: 'mi5x' },
    { topDes: '黑科技', img: phonePic, name: '小米Mix3', bottomDes: '3999元起', hrefPostfix: 'mi5x' },
    { topDes: '', img: phonePic, name: '查看全部', bottomDes: '小米手机', hrefPostfix: 'mi5x' },
  ],
  红米: [
    { topDes: '绝版', img: phonePic, name: '红米Note3', bottomDes: '998元起', hrefPostfix: 'mi5x' },
    { topDes: '新品', img: phonePic, name: '红米M3', bottomDes: '1288元起', hrefPostfix: 'mi5x' },
    { topDes: '', img: phonePic, name: '红米4 Pro', bottomDes: '1399元起', hrefPostfix: 'mi5x' },
  ],
  电视: [
    { topDes: '新品', img: phonePic, name: '小米电视3', bottomDes: '2999元起', hrefPostfix: 'mi5x' },
    { topDes: '新品', img: phonePic, name: '小米电视3 Pro', bottomDes: '3999元起', hrefPostfix: 'mi5x' },
    { topDes: '限量', img: phonePic, name: '小米电视-弧面屏', bottomDes: '5999元起', hrefPostfix: 'mi5x' },
  ],
  笔记本: [
    { topDes: '新品', img: phonePic, name: '小米Air2', bottomDes: '2999元起', hrefPostfix: 'mi5x' },
    { topDes: '黑科技', img: phonePic, name: '小米黑科技LT', bottomDes: '7999元起', hrefPostfix: 'mi5x' },
    { topDes: '', img: phonePic, name: '小米Air1', bottomDes: '3999元起', hrefPostfix: 'mi5x' },
    { topDes: '', img: phonePic, name: '小米Pro1', bottomDes: '3999元起', hrefPostfix: 'mi5x' },
    { topDes: '', img: phonePic, name: '小米Pro2', bottomDes: '4999元起', hrefPostfix: 'mi5x' },
    { topDes: '', img: phonePic, name: '查看全部', bottomDes: '小米手机', hrefPostfix: 'mi5x' },
  ],
  盒子: [
    { topDes: '', img: phonePic, name: '小米盒子家庭版', bottomDes: '199元起', hrefPostfix: 'mi5x' },
    { topDes: '', img: phonePic, name: '小米盒子旗舰版', bottomDes: '399元起', hrefPostfix: 'mi5x' },
  ],
  路由器: [
    { topDes: '新品', img: phonePic, name: '小米路由器', bottomDes: '233元起', hrefPostfix: 'mi5x' },
  ],
  智能硬件: [
    { topDes: '新品', img: phonePic, name: '小米吸尘器', bottomDes: '1888元起', hrefPostfix: 'mi5x' },
    { topDes: '爆款', img: phonePic, name: '小米空气净化器', bottomDes: '3999元起', hrefPostfix: 'mi5x' },
    { topDes: '', img: phonePic, name: '小米充电宝', bottomDes: '69元起', hrefPostfix: 'mi5x' },
    { topDes: '', img: phonePic, name: '小米家用套装', bottomDes: '999元起', hrefPostfix: 'mi5x' },
    { topDes: '', img: phonePic, name: '小米扫地机器人', bottomDes: '1999元起', hrefPostfix: 'mi5x' },
    { topDes: '', img: phonePic, name: '查看全部', bottomDes: '智能硬件', hrefPostfix: 'mi5x' },
  ],
};

export default {
  name: 'header-area',
  components: {
    SearchBox,
    ExpandMenu,
  },
  data() {
    return {
      showPopBlock: false,
      showExpandMenu: false,
      expandMenuCurContent: '',
      searchInitTags: [
        { name: '小米Mix2', count: 10 },
        { name: '小米6', count: 9 },
        { name: '红米Note3', count: 30 },
      ],
      navListMenu: [
        { name: '小米手机', href: '' },
        { name: '红米', href: '' },
        { name: '电视', href: '' },
        { name: '笔记本', href: '' },
        { name: '盒子', href: '' },
        { name: '新品', href: 'https://www.mi.com/p/2848.html' },
        { name: '路由器', href: '' },
        { name: '智能硬件', href: '' },
        { name: '服务', href: 'https://www.mi.com/service/' },
        { name: '社区', href: 'http://www.xiaomi.cn/' },
      ],
    };
  },
  methods: {
    hoverNavList(curName) {
      this.expandMenuCurContent = expandMenuContent[curName];
      this.showExpandMenu = this.expandMenuCurContent !== undefined;
    },
  },
};
</script>

<style lang="scss">
  @import '../assets/css/global';
  // 第一导航栏相关
  #header-container {
    background: #363636;
  }

  #site-header {
    margin: 0 auto;
    height: 40px;
    width: $site-content-width;
    display: flex;
    justify-content: space-between;
  }

  li {
    list-style: none;
  }

  a {
    text-decoration: none;
  }

  #site-header li a {
    color: $dark-dark-grey;
    font-size: 12px;
    line-height: 40px;
  }

  #left-header, #right-header {
    display: inline-block;
  }

  #site-header li {
    display: inline-block;
    margin: 0 5px;
    position: relative;
  }

  #site-header a:hover {
    color: white;
  }

  .split-right::after {
    content: '';
    width: 1px;
    height: 12px;
    background: #4A4A4A;
    position: absolute;
    top: 14px;
    right: -7px;
  }

  #site-header #cart {
    margin: 0;
    position: relative;
  }

  #cart-link {
    margin-left: 15px;
    margin-right: 0;
    display: inline-block;
    line-height: 40px;
    height: 40px;
    padding: 0 20px;
    background: $text-origin-grey;
  }

  .cart-hover {
    color: $mi-orange !important;
    background: white !important;
  }

  #pop-cart-block {
    position: absolute;
    right: 0;
    top: 40px;
    height: 100px;
    overflow: hidden;
    width: 300px;
    z-index: 1;
    background: white;
    box-shadow: 8px 0 8px -8px $shadow-color,
    -8px 0 8px -8px $shadow-color,
    0 1px 1px -1px $shadow-color;
    text-align: center;
    line-height: 100px;
    font-size: 12px;
  }

  .toggle-enter-active, .toggle-leave-active {
    transition-property: height;
    transition-duration: .3s;
    transition-timing-function: ease-in-out;
  }

  .toggle-enter, .toggle-leave-to {
    height: 0 !important;
  }

  .toggle-enter-to, .toggle-leave {
    height: 100px !important;
  }

  // 第二导航栏相关
  .site-nav-container {
    position: relative;
    width: 100%;
  }
  .site-nav {
    margin: 0 auto;
    height: 100px;
    width: $site-content-width;
  }

  .site-logo, .nav-list {
    float: left;
  }
  .nav-list {
    position: relative;
  }

  .sub-gg {
    width: 127px;
    height: 80px;
  }

  .nav-list > li {
    display: inline-block;
    line-height: 100px;
    padding: 0 10px;
    vertical-align: middle;
  }

  .nav-list li:hover {
    color: $mi-orange;
    cursor: pointer;
  }

  .site-logo {
    width: 55px;
    height: 55px;
    position: relative;
    top: 50%;
    transform: translateY(-50%);
    margin-right: 15px;
  }

  .search-box {
    float: right;
    height: 100px;
  }
  .exp-toggle-enter-active, .exp-toggle-leave-active {
    transition-property: height;
    transition-duration: .3s;
    transition-timing-function: ease-in-out;
    overflow: hidden !important;
  }

  .exp-toggle-enter, .exp-toggle-leave-to {
    height: 0 !important;
  }

  .exp-toggle-enter-to, .exp-toggle-leave {
    height: 230px !important;
    overflow: visible;
  }
  .expand-menu {
    position: absolute;
    top: 100px;
  }
</style>
