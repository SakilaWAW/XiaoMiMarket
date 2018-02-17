<template>
  <div class="gallery-more-info hover-shadow"><!--与GalleryAddonItem有大量重复代码 不符合DRY原则未找到好的解决方案-->
    <div class="container">
      <div class="addon-info">
        <a class="addon-name hover-cursor-pointer" :href="url">浏览更多</a>
        <a class="addon-desc hover-cursor-pointer" :href="url">{{ type }}</a>
      </div>
      <a :href="url"><i class="iconfont addon-img hover-cursor-pointer">&#xe63d;</i></a>
    </div>
  </div>
</template>

<script>

export default {
  name: 'gallery-more-info',
  props: [
    'url',
    'type',
  ],
};
</script>

<style lang="scss" scoped>
  @import "../../../../assets/css/global";
  .container {
    padding-left: 30px;
    position: relative;
    top: 50%;
    transform: translateY(-50%);
  }
  .addon-name {
    color: black;
    font-size: 20px;
  }
  .addon-desc {
    font-size: 12px;
    color: black;
    opacity: 0.6;
  }
  .addon-info {
    height: 42px;
    width: 94px;
    margin-right: 20px;
  }
  .addon-info, .addon-img {
    display: inline-block;
  }
  .addon-img {
    font-size: 50px;
    color: $mi-orange;
  }
</style>
