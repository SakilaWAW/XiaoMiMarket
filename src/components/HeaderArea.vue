<template>
  <div id="header-area">
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
        <li><a id="cart-link" href=""><i class="iconfont">&#xe60f;</i>购物车(0)</a></li>
      </ul>
    </div>
    <div class="site-nav">

    </div>
  </div>
</template>

<script>
export default {
  name: 'header-area',
};
</script>

<style lang="scss">
  #site-header {
    height: 40px;
    background: #363636;
    display: flex;
    justify-content: space-between;
  }
  li {
    list-style: none;
  }
  li a {
    text-decoration: none;
    color: #A2A2A2;
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
  #left-header {
    margin-left: 20px;
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
  #cart-link {
    margin: 0 15px;
    display:inline-block;
    line-height: 40px;
    height: 40px;
    padding: 0 20px;
    background: #444;
  }
  #right-header #cart-link:hover {
    color: #FF6829;
    background: white;
  }
  @font-face {
    font-family: 'iconfont';  /* project id 552033 */
    src: url('//at.alicdn.com/t/font_552033_p0b86r4q3b10dx6r.eot');
    src: url('//at.alicdn.com/t/font_552033_p0b86r4q3b10dx6r.eot?#iefix') format('embedded-opentype'),
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
</style>
