<template>
  <div id="app">
    <header-area></header-area>
    <content-area></content-area>
    <footer-area></footer-area>
  </div>
</template>

<script>
import HeaderArea from './components/HeaderArea';
import ContentArea from './components/ContentArea';
import FooterArea from './components/FooterArea';

export default {
  name: 'App',
  components: {
    HeaderArea,
    ContentArea,
    FooterArea,
  },
};
</script>

<style lang="scss">
  * {
    padding: 0;
    margin: 0;
  }
  body {
    min-width: 1240px;
    user-select:none;
  }
  @font-face {
    font-family: 'iconfont';  /* project id 552033 */
    src: url('//at.alicdn.com/t/font_552033_bbt20qh0p1zto6r.eot');
    src: url('//at.alicdn.com/t/font_552033_bbt20qh0p1zto6r.eot?#iefix')
        format('embedded-opentype'),
    url('//at.alicdn.com/t/font_552033_bbt20qh0p1zto6r.woff') format('woff'),
    url('//at.alicdn.com/t/font_552033_bbt20qh0p1zto6r.ttf') format('truetype'),
    url('//at.alicdn.com/t/font_552033_bbt20qh0p1zto6r.svg#iconfont') format('svg');
  }

  .iconfont {
    font-family: "iconfont" !important;
    font-size: 16px;
    font-style: normal;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    margin-right: 2px;
  }
  #app {
    font-family: "Helvetica Neue",Helvetica,Arial,
                "Microsoft Yahei","Hiragino Sans GB",
                "Heiti SC","WenQuanYi Micro Hei",sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
  }
</style>
