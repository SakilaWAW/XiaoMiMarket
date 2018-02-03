<template>
  <div class="indicate-points">
    <ul class="point-lis">
      <li class="point" v-for="i in totalCount" :key="i">
        <i class="iconfont point-img"
           :class="(i-1)===currentIdx?'point-selected':'point-nor'"
           @click="switchTo(i-1)">
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
  ],
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
  },
};
</script>

<style lang="scss" scoped>
  .indicate-points {
    position: absolute;
    bottom: 20px;
    right: 30px;
    z-index: 1;
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
  .point-nor {
    color: rgba(0,0,0,0.5);
  }
  .point-selected {
    color: rgba(255,255,255,0.5);
  }
</style>
