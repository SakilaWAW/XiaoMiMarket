<template>
  <div class="video-card" :style="{height: height + 'px', width: width + 'px'}">
    <div class="video-cover" @click="openSrc" :class="{'hover-cursor': isHover}"
         @mouseenter="isHover=true" @mouseleave="isHover=false">
      <img :src="item.img">
      <div class="play-btn" :class="{'play-btn-hover': isHover}"
           @mouseenter="isHover=true">
        <i class="iconfont">&#xe620;</i>
      </div>
    </div>
    <p class="desc" @click="openSrc">{{ item.desc }}</p>
    <p class="sub-desc">{{ item.subDesc }}</p>
  </div>
</template>

<script>
export default {
  name: 'video-card',
  props: [
    'item',
    'width',
    'height',
  ],
  data() {
    return {
      isHover: false,
    };
  },
  methods: {
    openSrc() {
      this.$emit('openSrc', this.item.videoSrc);
    },
  },
};
</script>

<style lang="scss" scoped>
  @import '../../../assets/css/global';
  .video-card {
    background: white;
    text-align: center;
  }
  .video-cover {
    position: relative;
  }
  .play-btn {
    position: absolute;
    left: 20px;
    bottom: 10px;
    color: white;
    height: 20px;
    width: 35px;
    background: rgba(0,0,0, 0.3);
    border: 2px solid white;
    border-radius: 12px;
    transition: all .15s ease-in-out;
  }
  .play-btn i {
    position: relative;
    left: 2px;
    top: 3px;
    font-size: 13px;
  }
  .hover-cursor {
    cursor: pointer;
  }
  .play-btn-hover {
    border-color: $mi-orange;
    background: $mi-orange;
    cursor: pointer;
  }
  .desc {
    font-size: 14px;
    margin: 25px 0 10px 0;
  }
  .desc:hover {
    color: $mi-orange;
    cursor: pointer;
  }
  .sub-desc {
    font-size: 12px;
    color: $dark-dark-grey;
  }
</style>
