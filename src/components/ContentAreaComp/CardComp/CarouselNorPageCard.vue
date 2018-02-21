<template>
  <div class="carousel-nor-page-card" :style="{width: width + 'px', height: height + 'px'}">
    <a :href="page.href"><span class="title">{{ page.title }}</span></a>
    <a :href="page.href"><span class="desc">{{ page.desc }}</span></a>
    <a :href="page.href"><span class="price">{{ page.price }}</span></a>
    <a class="img" :href="page.href"><img :src="page.img"></a>
  </div>
</template>

<script>
export default {
  name: 'carousel-nor-page-card',
  props: [
    'height',
    'width',
    'page',
  ],
};
</script>

<style lang="scss" scoped>
  .carousel-nor-page-card * {
    display: block;
  }
  .carousel-nor-page-card *:hover {
    cursor: pointer;
  }
  .img img{
    margin: 0 auto;
  }
  .title {
    color: black;
    font-size: 20px;
  }
  .desc {
    margin: 10px 35px;
    font-size: 12px;
    color: #AAA;
  }
  .price {
    color: black;
    margin-bottom: 20px;
    font-size: 14px;
  }
</style>
