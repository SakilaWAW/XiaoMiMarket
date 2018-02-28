<!--
h5播放器弹出框组件
使用方法：
popup-html5-player
  ...

传参：
videoSrc  视频地址
title     弹出框标题
isHide    控制弹出层的开关
@close    点击关闭按钮时父控件中的调用函数
-->

<template>
  <div class="shelter" v-if="!isHide">
    <div class="video-player">
      <div class="header">
        <span class="video-title">{{ title }}</span>
        <i class="iconfont close-icon" @click="closeLayer">&#xe632;</i>
      </div>
      <video controls preload="metadata" :src="videoSrc"></video>
    </div>
  </div>
</template>

<script>
export default {
  name: 'popup-html5-player',
  props: [
    'title',
    'isHide',
    'videoSrc',
  ],
  methods: {
    closeLayer() {
      this.$emit('close');
    },
  },
};
</script>

<style lang="scss" scoped>
  @import '../../../assets/css/global';
  .shelter {
    height: 100%;
    width: 100%;
    position: fixed;
    top: 0;
    left: 0;
    z-index: 99;
    background: rgba(0,0,0, 0.3);
  }
  .video-player {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translateY(-50%) translateX(-50%);
    background: white;
  }
  video {
    width: 880px;
    height: 536px;
    background: black;
    display: block;
  }
  .header {
    height: 60px;
    padding: 0 30px;
    position: relative;
  }
  .video-title {
    font-size: 18px;
    line-height: 60px;
  }
  .close-icon {
    position: absolute;
    right: 15px;
    line-height: 60px;
    font-size: 30px;
  }
  .close-icon:hover {
    color: $mi-orange;
    cursor: pointer;
  }
</style>
