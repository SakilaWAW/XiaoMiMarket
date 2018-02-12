<template>
  <div class="gallery-content">
    <div class="left-content">
      <a class="l-content-item hover-shadow" v-for="(item, index) in dataMap.leftBar"
           :href="item.href" :key="index" :style="{background: `url(${item.img})`}"></a>
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
  @import "../../../assets/css/global";
  .gallery-content {
    height: 614px;
    width: 100%;
    font-size: 0;
  }
  .left-content, .right-content {
    height: 100%;
  }
  .left-content {
    display: inline-flex;
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
