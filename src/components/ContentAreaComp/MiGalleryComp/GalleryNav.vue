<template>
  <ul class="gallery-nav">
    <li class="g-nav-item" v-for="(nav, index) in navList" :key="index">
      <span>{{ nav.txt }}</span>
    </li>
  </ul>
</template>

<script>
export default {
  name: 'gallery-nav',
  props: [
    'currentIdx',
  ],
  data() {
    return {
      navList: [
        { txt: '热门' },
        { txt: '电视影音' },
        { txt: '电脑' },
        { txt: '家具' },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
  .gallery-nav {
    font-size: 0;
    height: 100%;
    position: absolute;
    right: 0;
    top: 0;
  }
  .g-nav-item {
    font-size: 16px;
    display: inline-block;
    height: 100%;
    margin-left: 20px;
    box-sizing: border-box;
  }
  .g-nav-item a {
    color: black;
  }
  .gallery-title, .gallery-nav {
    line-height: 58px;
  }
</style>
