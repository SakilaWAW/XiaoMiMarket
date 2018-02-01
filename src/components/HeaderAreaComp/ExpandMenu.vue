<template>
  <div class="expand-menu">
    <ul class="menu-container">
      <li class="menu-item"
          v-for="(item, index) in items"
          :key="item.name"
          :class="{'right-sep-line': index<5}">
        <span class="top-des" v-if="item.hasDes">{{ item.topDes }}</span>
        <a class="item-img" :href="`https://www.mi.com/${item.hrefPostfix}`" :style="{background: `url(${item.img})`}"></a>
        <a class="item-name" :href="`https://www.mi.com/${item.hrefPostfix}`">{{ item.name }}</a>
        <span :class="{'orange-text': isOrangeDes(item.name)}">{{ item.bottomDes }}</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'expand-menu',
  props: ['items'],
  methods: {
    isOrangeDes(name) {
      return name !== '查看全部';
    },
  },
};
</script>

<style lang="scss" scoped>
  @import '../../assets/css/global';
  $menu-height: 230px;
  .expand-menu {
    width: 100%;
    height: $menu-height;
    background: white;
    border-top: 1px solid $shadow-grey;
    box-shadow: 0 5px 4px -4px $shadow-grey;// 单侧投影技巧
  }
  .menu-container {
    display: flex;
    width: $site-content-width;
    height: $menu-height;
    margin: 0 auto;
  }

  .menu-item {
    position: relative;
    text-align: center;
    width: 201px;
    margin-right: 5px;
    height: $menu-height;
    font-size: 12px;
  }
  .menu-item:nth-child(1) {
    margin-left: 5px;
  }
  .top-des {
    border: 1px solid $mi-orange;
    line-height: 22px;
    height: 22px;
    width: 66px;
    position: absolute;
    top: -1px;
    right: 50%;
    transform: translateX(50%);
    color: $mi-orange;
  }
  .item-img {
    height: 110px;
    width: 160px;
    display: block;
    margin: 40px auto 16px auto;
  }
  .item-name {
    margin-bottom: 2px;
    color: black;
    display: block;
  }
  .orange-text {
    color: $mi-orange;
  }
  .right-sep-line::after {
    content: "";
    width: 1px;
    height: 100px;
    position: absolute;
    top: 45px;
    right: 0;
    background: $shadow-grey;
  }
</style>
