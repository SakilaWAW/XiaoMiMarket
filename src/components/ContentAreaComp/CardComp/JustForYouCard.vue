<template>
  <div class="just-for-you-card hover-shadow">
    <a class="item-href-pic" :href="item.href" :style="{background: `url(${item.img})`}"></a>
    <span class="item-name"><a :href="item.href">{{ item.name }}</a></span>
    <span class="item-desc">{{ item.price }}</span>
    <span class="item-sub-desc">{{ item.subDesc }}</span>
  </div>
</template>

<script>
export default {
  name: 'just-for-you-card',
  props: [
    'item',
  ],
};
</script>

<style lang="scss" scoped>
  @import '../../../assets/css/global';
  $text-grey: #AAA;
  $shallow-grey: #FAFAFA;
  .just-for-you-card {
    border-top: 1px solid white;
    box-sizing: border-box;
    width: 100%;
    height: 100%;
    background: white;
  }
  .item-href-pic, .item-name, .item-desc, .item-sub-desc {
    display: block;
  }
  .item-href-pic {
    margin: 40px auto 30px auto;
    height: 140px;
    width: 140px;
  }
  .item-name a {
    display: block;
    margin: 0 25px;
    color: black;
    font-size: 14px;
    text-overflow: ellipsis;
    overflow: hidden;
    white-space: nowrap;
  }
  .item-desc {
    margin-top: 3px;
    margin-bottom: 8px;
    font-size: 14px;
    color: $mi-orange;
  }
  .item-sub-desc {
    font-size: 14px;
    color: $text-grey;
  }
</style>
