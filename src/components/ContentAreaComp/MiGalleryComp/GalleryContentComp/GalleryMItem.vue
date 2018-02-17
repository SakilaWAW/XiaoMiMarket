<template>
  <div class="gallery-m-item hover-shadow"
       @mouseleave="isHover=false" @mouseenter="isHover=true">
    <span class="top-desc" v-show="currentItem.topDesc!==''">{{ currentItem.topDesc }}</span>
    <a :href="currentItem.url"><img class="item-img" :src="currentItem.img"></a>
    <a :href="currentItem.url" class="item-name">{{ currentItem.name }}</a>
    <span class="item-sub-desc">{{ currentItem.subDesc }}</span>
    <span class="item-price">{{ currentItem.price }}</span>
    <span class="item-o-price" v-if="currentItem.oPrice!==undefined">{{ currentItem.oPrice }}</span>
    <transition name="slide">
      <div class="item-comment hover-cursor-pointer"
           v-show="isHover"
           @click="jumpTo(currentItem.url)">
        <span class="comment-txt">{{ filtedComment }}</span>
        <span class="comment-author">{{ currentItem.author }}</span>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'gallery-m-item',
  props: [
    'currentItem',
  ],
  data() {
    return {
      isHover: false,
    };
  },
  computed: {
    filtedComment() {
      const comt = this.currentItem.comment;
      return comt.length <= 26 ? comt : `${comt.substr(0, 26)}...`;
    },
  },
  methods: {
    jumpTo(url) {
      window.location.href = url;
    },
  },
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
    overflow: hidden;
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
    margin: 40px auto 14px auto;
  }
  .item-name {
    color: black;
    font-size: 14px;
  }
  .item-sub-desc {
    font-size: 12px;
    color: $dark-dark-grey;
    margin-bottom: 8px;
  }
  .item-price {
    display: inline-block;
    font-size: 14px;
    color: $mi-orange;
  }
  .item-o-price {
    display: inline-block;
    font-size: 14px;
    color: $shadow-color;
    text-decoration: line-through;
  }
  // 评论
  .item-comment {
    box-sizing: border-box;
    width: 100%;
    height: 75px;
    background: $mi-orange;
    position: absolute;
    bottom: 0;
    padding: 5px 25px;
  }
  .item-comment span {
    text-align: left;
    display: block;
    color: white;
    font-size: 12px;
  }
  .comment-txt {
    height: 36px;
    margin-bottom: 10px;
  }
  .comment-author {
    opacity: 0.6;
  }
  .slide-enter, .slide-leave-to {
    bottom: -75px;
  }
  .slide-enter-to, .slide-leave {
    bottom: 0;
  }
  .slide-enter-active, .slide-leave-active {
    transition: bottom .3s ease-in-out;
  }
</style>
