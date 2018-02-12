<template>
  <div class="gallery-m-item">
    <span class="top-desc" v-show="currentItem.topDesc!==''">{{ currentItem.topDesc }}</span>
    <img class="item-img" :src="currentItem.img">
    <span class="item-name">{{ currentItem.name }}</span>
    <span class="item-sub-desc">{{ currentItem.subDesc }}</span>
    <span class="item-price">{{ currentItem.price }}</span>
  </div>
</template>

<script>
export default {
  name: 'gallery-m-item',
  props: [
    'currentItem',
  ],
};
</script>

<style lang="scss" scoped>
  @import '../../../../assets/css/global';
  .gallery-m-item {
    display: inline-block;
    width: 234px;
    height: 300px;
    margin-right: 19px;
    text-align: center;
    background: white;
    position: relative;
  }
  .gallery-m-item * {
    display: block;
  }
  .top-desc {
    font-size: 12px;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    position: absolute;
    background: $mi-orange;
    color: white;
    padding: 3px 15px;
  }
  .item-img {
    height: 150px;
    width: 150px;
    margin: 55px auto 14px auto;
  }
  .item-name {
    font-size: 14px;
  }
  .item-sub-desc {
    font-size: 12px;
    color: $dark-dark-grey;
  }
  .item-price {
    font-size: 14px;
    color: $mi-orange;
  }
</style>
