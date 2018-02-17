<template>
  <ul class="gallery-nav">
    <li class="g-nav-item" v-for="(type, index) in typeList" :key="index">
      <span class="hover-cursor-pointer" :class="{'hover-status': isSelected(index)}"
            @mouseenter="switchTo(index)">{{ type }}</span>
      <transition name="opacity">
        <div class="nav-underline" v-show="isSelected(index)"></div>
      </transition>
    </li>
  </ul>
</template>

<script>
export default {
  name: 'gallery-nav',
  props: [
    'typeList',
    'currentIdx',
  ],
  methods: {
    switchTo(idx) {
      this.$emit('pageTo', idx);
    },
    isSelected(idx) {
      return this.currentIdx === idx;
    },
  },
};
</script>

<style lang="scss" scoped>
  @import '../../../assets/css/global';
  .gallery-nav {
    font-size: 0;
    height: 100%;
    position: absolute;
    right: 0;
    top: 0;
    line-height: 58px;
  }
  .g-nav-item {
    font-size: 16px;
    display: inline-block;
    position: relative;
    height: 100%;
    margin-left: 20px;
    box-sizing: border-box;
  }
  .hover-status {
    color: $mi-orange;
  }
  .nav-underline {
    position: absolute;
    bottom: 16px;
    left: 0;
    width: 100%;
    height: 2px;
    background: $mi-orange;
  }
  .opacity-enter, .opacity-leave-to {
    opacity: 0;
  }
  .opacity-enter-to, .opacity-leave {
    opacity: 1;
  }
  .opacity-enter-active, .opacity-leave-active {
    transition: opacity .2s ease-in-out;
  }
</style>
