<template>
  <div class="hot-item-card hover-shadow">
    <a :href="item.href"><img :src="item.img"></a>
    <div class="info">
      <a class="comment" :href="item.href">{{ filtedComment }}</a>
      <span class="author">{{ item.author }}</span>
      <a class="name" :href="item.href">{{ item.name }}</a>
      <span class="price">{{ item.price }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'hot-item-card',
  props: [
    'item',
  ],
  computed: {
    filtedComment() {
      const comt = this.item.comment;
      return comt.length <= 50 ? comt : `${comt.substr(0, 50)}...`;
    },
  },
};
</script>

<style lang="scss" scoped>
  @import '../../../assets/css/global';
  .hot-item-card {
    height: 100%;
    width: 100%;
    margin-bottom: 20px;
    font-size: 0;
    background: white;
  }
  .comment {
    margin-bottom: 20px;
    color: black;
  }
  .info {
    margin: 20px 25px;
  }
  .comment, .author {
    display: block;
    overflow: hidden;
    font-size: 14px;
  }
  .author {
    color: $shadow-color;
  }
  .name, .price {
    display: inline-block;
    font-size: 13px;
    margin-top: 10px;
  }
  .name {
    color: black;
    margin-right: 20px;
    position: relative;
  }
  .price {
    color: $mi-orange;
  }
  .name::after {
    content: "";
    position: absolute;
    height: 12px;
    width: 1px;
    background: grey;
    right: -10px;
    top: 5px;
  }
</style>
