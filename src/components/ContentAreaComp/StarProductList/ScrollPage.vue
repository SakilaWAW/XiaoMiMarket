<template>
  <div class="scroll-page">
    <ul class="container" :style="{'min-width': ulWidth + 'px','margin-left': leftMargin + 'px'}">
      <li class="star-item" v-for="(item, index) in itemList" :key="index"
            :style="{'border-top': `1px solid ${borderColor(index)}`}">
        <a class="item-href-pic" :href="item.href" :style="{background: `url(${item.img})`}"></a>
        <span class="item-name"><a :href="item.href">{{ item.name }}</a></span>
        <span class="item-desc">{{ item.desc }}</span>
        <span class="item-sub-desc">{{ item.subDesc }}</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'scroll-page',
  props: [
    'itemList',
    'currentPage',
  ],
  data() {
    return {
      isScrollFront: false,
      isScrollBack: false,
    };
  },
  computed: {
    ulWidth() {
      return (this.itemList.length / 5) * 1240;
    },
    leftMargin() {
      return -(1240 * this.currentPage);
    },
  },
  methods: {
    borderColor(idx) {
      const colorMap = ['red', 'goldenrod', 'blue', 'green', 'pink'];
      return colorMap[idx % 5];
    },
  },
};
</script>

<style lang="scss" scoped>
  @import '../../../assets/css/global';
  $shallow-grey: #FAFAFA;
  $text-grey: #AAA;
  .scroll-page {
    width: 100%;
    height: 340px;
    overflow-x: hidden;
    margin-bottom: 40px;
  }
  .container {
    font-size: 0;
    display: block;
    text-align: center;
    height: 100%;
    transition: margin-left .8s ease-in-out;
  }
  .star-item {
    box-sizing: border-box;
    font-size: 16px;
    display: inline-block;
    width: 234px;
    margin-right: 17.5px;
    height: 100%;
    background: $shallow-grey;
  }
  .star-item:nth-child(5n) {
    margin-right: 0;
  }
  .item-href-pic, .item-name, .item-desc, .item-sub-desc {
    display: block;
  }
  .item-href-pic {
    margin: 40px auto 30px auto;
    height: 160px;
    width: 160px;
  }
  .item-name a {
    color: black;
  }
  .item-desc {
    margin-top: 3px;
    margin-bottom: 12px;
    font-size: 12px;
    color: $text-grey;
  }
  .item-sub-desc {
    color: $mi-orange;
  }
</style>
