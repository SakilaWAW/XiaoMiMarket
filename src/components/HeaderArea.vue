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
                   @mouseleave="showPopBlock=false" v-show="showPopBlock">购物车中还没有商品，赶紧选购吧！
              </div>
            </transition>
          </li>
        </ul>
      </div>
    </div>
    <div class="site-nav">
      <div class="site-logo">
        <a class="logo-container" href="https://www.baidu.com">
          <img class="mi-logo" src="../assets/mi_logo.png" alt="">
        </a>
      </div>
      <ul class="nav-list">
        <li class="sub-gg"><a href=""></a></li>
        <li><a href="">小米手机</a></li>
        <li><a href="">红米</a></li>
        <li><a href="">电视</a></li>
        <li><a href="">笔记本</a></li>
        <li><a href="">盒子</a></li>
        <li><a href="">新品</a></li>
        <li><a href="">路由器</a></li>
        <li><a href="">智能硬件</a></li>
        <li><a href="">服务</a></li>
        <li><a href="">社区</a></li>
      </ul>
      <div class="search-container">
        <form class="search-form" action="">
          <label for="GET-name"></label>
          <input class="search-input" id="GET-name" type="text" name="name">
          <input class="search-btn iconfont" type="submit" value="&#xe60f;">
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'header-area',
  data() {
    return {
      showPopBlock: false,
    };
  },
};
</script>

<style lang="scss">
  $mi-orange: #FF6829;
  $shadow-color: #CCC;
  $dark-dark-grey: #A2A2A2;
  $text-origin-grey: #444;
  // 第一导航栏相关
  #header-container {
    background: #363636;
  }
  #site-header {
    margin: 0 auto;
    height: 40px;
    width: 1240px;
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
  #site-header li{
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
    display:inline-block;
    line-height: 40px;
    height: 40px;
    padding: 0 20px;
    background: $text-origin-grey;
  }
  .cart-hover {
    color: $mi-orange !important;
    background: white !important;
  }
  @font-face {
    font-family: 'iconfont';  /* project id 552033 */
    src: url('//at.alicdn.com/t/font_552033_p0b86r4q3b10dx6r.eot');
    src: url('//at.alicdn.com/t/font_552033_p0b86r4q3b10dx6r.eot?#iefix')
        format('embedded-opentype'),
    url('//at.alicdn.com/t/font_552033_p0b86r4q3b10dx6r.woff') format('woff'),
    url('//at.alicdn.com/t/font_552033_p0b86r4q3b10dx6r.ttf') format('truetype'),
    url('//at.alicdn.com/t/font_552033_p0b86r4q3b10dx6r.svg#iconfont') format('svg');
  }
  .iconfont {
    font-family:"iconfont" !important;
    font-size:16px;
    font-style:normal;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    margin-right: 2px;
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
  .site-nav {
    margin: 0 auto;
    height: 100px;
    width: 1240px;
    background: darkgrey;
    position: relative;
  }
  .site-logo, .nav-list{
    float: left;
  }
  .sub-gg {
    width: 127px;
    height: 80px;
  }
  .nav-list li{
    display: inline-block;
    line-height: 100px;
    margin: 0 10px;
    vertical-align: middle;
  }
  .nav-list li a {
    color: black;
  }
  .nav-list li a:hover {
    color: $mi-orange;
  }
  .site-logo {
    width: 55px;
    height: 55px;
    position: relative;
    top: 50%;
    transform: translateY(-50%);
    margin-right: 15px;
  }
  .search-form {
    height: 50px;
    position: relative;
    top: 50%;
    transform: translateY(-50%);
  }
  .search-container {
    float: right;
    height: 100px;
  }
  .search-form input {
    height: 50px;
    vertical-align: middle;
  }
  .search-input {
    width: 245px;
    position: relative;
    left: 5px;
    top: 1px;
    border: 1px solid black;
  }
  .search-btn {
    width: 50px;
    background: white;
    box-sizing: content-box;
    border: 1px solid black;
  }
</style>
