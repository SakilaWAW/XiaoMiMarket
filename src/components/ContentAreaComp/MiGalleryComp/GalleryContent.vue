<template>
  <div class="gallery-content">
    <div class="left-content">
      <a class="l-content-item hover-shadow" v-for="(item, index) in leftBarMap"
         :href="item.href" :key="index"
         :style="{background: `url(${item.img})`, height: leftBlockHeight}"
         :class="{'margin-bottom-14': leftBlockHasBottomMargin(index)}"></a>
    </div>
    <div class="right-content">
      <gallery-m-item v-for="(item, idx) in currentContent.nor" :key="idx"
                      :currentItem="item"
                      :class="{'clear-right-margin': isRightest(idx),
                                    'bottom-margin': hasBottomMargin(idx)}">
      </gallery-m-item>
      <div class="addon-container">
        <gallery-addon-item :addonInfo="currentContent.addOn"></gallery-addon-item>
        <gallery-more-info :type="currentType"
                           :url="currentContent.moreUrl"
                           :moreInfo="true"></gallery-more-info>
      </div>
    </div>
  </div>
</template>

<script>
import GalleryMItem from './GalleryContentComp/GalleryMItem';
import GalleryAddonItem from './GalleryContentComp/GalleryAddonItem';
import GalleryMoreInfo from './GalleryContentComp/GalleryMoreInfo';

export default {
  name: 'gallery-content',
  components: {
    GalleryMItem,
    GalleryAddonItem,
    GalleryMoreInfo,
  },
  props: [
    'leftBarMap',
    'currentContent',
    'currentType',
  ],
  methods: {
    isRightest(idx) {
      return idx % 4 === 3;
    },
    hasBottomMargin(idx) {
      return Math.floor(idx / 4) === 0;
    },
    leftBlockHasBottomMargin(idx) {
      return idx !== (this.leftBarMap.length - 1);// 非最后一个就有margin-bottom
    },
  },
  computed: {
    leftBlockHeight() {
      return (614 - ((this.leftBarMap.length - 1) * 14)) / this.leftBarMap.length;
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
  .margin-bottom-14 {
    margin-bottom: 14px;
  }
  .clear-right-margin {
    margin-right: 0!important;
  }
  .bottom-margin {
    margin-bottom: 14px;
  }
  .addon-container {
    vertical-align: top;
    display: inline-block;
    width: 234px;
    height: 300px;
  }
  .gallery-addon-item, .gallery-more-info {
    height: 143px;
    width: 100%;
    background: white;
    font-size: 14px;
    margin-bottom: 14px;
  }
</style>
