<template>
  <div class="gallery-content">
    <div class="left-content">
      <a class="l-content-item hover-shadow" v-for="(item, index) in leftBarMap"
           :href="item.href" :key="index" :style="{background: `url(${item.img})`}"></a>
    </div>
    <div class="right-content">
      <gallery-m-item v-for="(currentItem, idx) in currentItems" :key="idx"
                      :currentItem="currentItem"
                      :class="{'clear-right-margin': isRightest(idx), 'bottom-margin': hasBottomMargin(idx)}">
      </gallery-m-item>
    </div>
  </div>
</template>

<script>
import GalleryMItem from './MiGalleryComp/GalleryMItem';

export default {
  name: 'gallery-content',
  components: {
    GalleryMItem,
  },
  props: [
    'leftBarMap',
    'currentItems',
  ],
  methods: {
    isRightest(idx) {
      return idx % 4 === 3;
    },
    hasBottomMargin(idx) {
      return Math.floor(idx / 4) === 0;
    },
  },
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
    vertical-align: top;
    flex-direction: column;
    justify-content: space-between;
    width: 234px;
    margin-right: 13px;
  }
  .right-content {
    display: inline-block;
    width: 993px;
    font-size: 0;
  }
  .l-content-item {
    height: 100%;
  }
  .clear-right-margin {
    margin-right: 0!important;
  }
  .bottom-margin {
    margin-bottom: 14px;
  }
</style>
