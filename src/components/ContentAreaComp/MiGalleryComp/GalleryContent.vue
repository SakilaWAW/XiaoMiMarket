<template>
  <div class="gallery-content">
    <div class="left-content">
      <div class="l-content-item" v-for="(item, index) in dataMap.leftBar"
           :href="item.href" :key="index" :style="{background: `url(${item.img})`}"></div>
    </div>
    <div class="right-content">

    </div>
  </div>
</template>

<script>
export default {
  name: 'gallery-content',
  props: [
    'dataMap',
  ],
};
</script>

<style lang="scss" scoped>
  .gallery-content {
    height: 614px;
    width: 100%;
    font-size: 0;
  }
  .left-content, .right-content {
    height: 100%;
  }
  .left-content {
    display: inline-block;
    flex-direction: column;
    justify-content: space-between;
    width: 234px;
    margin-right: 14px;
    background: yellow;
  }
  .right-content {
    display: inline-block;
    width: 992px;
    background: #CCC;
  }
  .l-content-item {
    height: 100%;
  }
</style>
