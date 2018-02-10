<template>
  <div class="mi-gallery">
    <div class="gallery-header">
      <span class="gallery-title">{{ title }}</span>
      <gallery-nav></gallery-nav>
    </div>
    <gallery-content></gallery-content>
  </div>
</template>

<script>
import GalleryNav from './MiGalleryComp/GalleryNav';
import GalleryContent from './MiGalleryComp/GalleryContent';

export default {
  name: 'mi-gallery',
  props: [
    'title',
  ],
  components: {
    GalleryNav,
    GalleryContent,
  },
  data() {
    return {};
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
