<template>
  <div class="mi-gallery">
    <div class="gallery-header">
      <span class="gallery-title">{{ dataList.name }}</span>
      <gallery-nav :typeList="dataList.types"
                   @pageTo="switchToPage"
                   :currentIdx="currentIdx"></gallery-nav>
    </div>
    <gallery-content :leftBarMap="dataList.leftBar"
                     :currentContent="currentContent"
                     :currentType="currentType"></gallery-content>
  </div>
</template>

<script>
import GalleryNav from './MiGalleryComp/GalleryNav';
import GalleryContent from './MiGalleryComp/GalleryContent';

export default {
  name: 'mi-gallery',
  props: [
    'dataList',
  ],
  components: {
    GalleryNav,
    GalleryContent,
  },
  data() {
    return {
      currentIdx: 0,
    };
  },
  computed: {
    currentContent() {
      return this.dataList.items[this.currentIdx];
    },
    currentType() {
      return this.dataList.types[this.currentIdx];
    },
  },
  methods: {
    switchToPage(idx) {
      this.currentIdx = idx;
    },
  },
};
</script>

<style lang="scss" scoped>
  @import '../../assets/css/global';
  .gallery-header {
    height: 58px;
    position: relative;
  }
  .gallery-title {
    font-size: 22px;
  }
</style>
