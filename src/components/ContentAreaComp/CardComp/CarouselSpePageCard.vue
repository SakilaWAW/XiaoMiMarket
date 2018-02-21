<template>
  <div class="carousel-spe-page-card" :style="{width: width + 'px', height: height + 'px'}">
    <span class="desc">{{ page.desc }}</span>
    <a class="more" :href="page.href"
       :style="{color: isHover?'white':btnColor, 'border-color': btnColor,
                background: isHover?btnColor:'transparent'}"
       @mouseenter="isHover=true"
       @mouseleave="isHover=false">
      {{ page.moreBtnTxt }}
    </a>
    <a class="img" :href="page.href"><img :src="page.img"></a>
  </div>
</template>

<script>
export default {
  name: 'carousel-spe-page-card',
  props: [
    'height',
    'width',
    'page',
    'btnColor',
  ],
  data() {
    return {
      isHover: false,
    };
  },
};
</script>

<style lang="scss" scoped>
  .carousel-spe-page-card * {
    display: block;
  }
  .img img{
    margin: 0 auto;
  }
  .title {
    font-size: 20px;
  }
  .desc {
    font-size: 12px;
    margin: 10px 35px 30px 35px;
    color: #AAA;
  }
  .more {
    display: inline;
    font-size: 14px;
    padding: 5px 15px;
    border: 1px solid black;
    transition: background .3s ease-in-out, color .3s ease-in-out;
  }
  .img {
    margin-top: 30px;
  }
</style>
