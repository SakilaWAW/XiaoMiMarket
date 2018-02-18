<template>
  <div class="mi-card" :style="{'border-top': `1px solid ${borderColor(index)}`}">
    <a class="item-href-pic" :href="item.href" :style="{background: `url(${item.img})`}"></a>
    <span class="item-name"><a :href="item.href">{{ item.name }}</a></span>
    <span class="item-desc">{{ item.desc }}</span>
    <span class="item-sub-desc">{{ item.subDesc }}</span>
  </div>
</template>

<script>
export default {
  name: 'mi-card',
  props: [
    'item',
    'index',
  ],
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
  $text-grey: #AAA;
  $shallow-grey: #FAFAFA;
  .mi-card {
    box-sizing: border-box;
    width: 100%;
    height: 100%;
    background: $shallow-grey;
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
