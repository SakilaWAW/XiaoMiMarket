<template>
  <div class="mi-star-product-card" :style="{'border-top-color': borderColor}">
    <a class="item-href-pic" :href="item.href" :style="{background: `url(${item.img})`}"></a>
    <span class="item-name"><a :href="item.href">{{ item.name }}</a></span>
    <span class="item-desc">{{ item.desc }}</span>
    <span class="item-sub-desc">{{ item.subDesc }}</span>
  </div>
</template>

<script>
export default {
  name: 'mi-star-product-card',
  props: [
    'item',
    'index',
  ],
  computed: {
    borderColor() {
      const colorMap = ['red', 'goldenrod', 'blue', 'green', 'pink'];
      return colorMap[this.index % 5];
    },
  },
};
</script>

<style lang="scss" scoped>
  @import '../../../assets/css/global';
  $text-grey: #AAA;
  $shallow-grey: #FAFAFA;
  .mi-star-product-card {
    border-top: 1px solid black;
    box-sizing: border-box;
    width: 100%;
    height: 100%;
    background: $shallow-grey;
  }
  .item-href-pic, .item-name, .item-desc, .item-sub-desc {
    display: block;
  }
  .item-href-pic {
    margin: 40px auto 30px auto;
    height: 160px;
    width: 160px;
  }
  .item-name a {
    color: black;
    font-size: 14px;
  }
  .item-desc {
    margin-top: 3px;
    margin-bottom: 12px;
    font-size: 12px;
    color: $text-grey;
  }
  .item-sub-desc {
    color: $mi-orange;
    font-size: 14px;
  }
</style>
