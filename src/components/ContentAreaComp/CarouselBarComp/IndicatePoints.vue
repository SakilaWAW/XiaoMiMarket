<!--
指示点组件
使用方式：
indicate-points
:totalCount     总数
:currentCount   当前位置(从0开始)
:norColor       平常的颜色
:hoverColor     hover时的颜色
:selectedColor  选中时的颜色
@switchTo(idx)  切换到idx位置时的操作
-->

<template>
  <div class="indicate-points">
    <ul class="point-lis">
      <li class="point" v-for="i in totalCount" :key="i">
        <i class="iconfont point-img"
           :style="{color: getColor(i-1)}"
           @click="switchTo(i-1)"
           @mouseenter="hover(i-1)" @mouseleave="unhover()">
          &#xe82f;
        </i>
      </li>
    </ul>
  </div>
</template>

<script>
export default { // 所有下标从0开始算
  name: 'indicate-points',
  props: [
    'totalCount',
    'currentCount',
    'norColor',
    'hoverColor',
    'selectedColor',
  ],
  data() {
    return {
      hoverIdx: -1,
    };
  },
  computed: {
    currentIdx: {
      get() {
        return this.currentCount;
      },
      set(newIdx) {
        this.$emit('switchTo', newIdx);
      },
    },
  },
  methods: {
    switchTo(targetAbsIdx) {
      this.currentIdx = targetAbsIdx;
    },
    isSelected(idx) {
      return idx === this.currentIdx;
    },
    isHover(idx) {
      return idx === this.hoverIdx;
    },
    getColor(idx) {
      if (this.isSelected(idx)) return this.selectedColor;
      else if (this.isHover(idx)) return this.hoverColor;
      return this.norColor;
    },
    hover(idx) {
      this.hoverIdx = idx;
    },
    unhover() {
      this.hoverIdx = -1;
    },
  },
};
</script>

<style lang="scss" scoped>
  .indicate-points {
    display: flex;
    flex-direction: row;
  }
  .point {
    display: inline-block;
    margin-left: 3px;
  }
  .indicate-points .point-img {
    font-size: 25px;
  }
  .indicate-points .point-img:hover {
    cursor: pointer;
  }
</style>
