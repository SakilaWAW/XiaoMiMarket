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

<style>
  * {
    padding: 0;
    margin: 0;
  }
  body {
    min-width: 1240px;
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
