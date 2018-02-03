<template>
  <div class="carousel-expand-menu" :style="{width: columnNum*251+2+'px'}"
       @mouseenter="hover" @mouseleave="leave">
    <!--<ul :style="{ 'column-count': columnNum }"> columns方法也可以控制列数 但是没法控制每列的个数 残念-->
    <ul>
      <li class="ca-expand-item" v-for="(item, index) in menuData" :key="index"
          @click="jumpTo(item.href)"
          :style="{'top': 2+index%6*76+'px', 'left': 1+Math.floor(index/6)*251+'px'}">
        <div class="ca-expand-item-img" :style="{background:`url(${item.img})`}"></div>
        <span class="ca-expand-item-desc"> {{ item.desTxt }} </span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'carousel-expand-menu',
  props: ['menuData'],
  computed: {
    columnNum() {
      return Math.ceil(this.menuData.length / 6);
    },
  },
  methods: {
    jumpTo(url) {
      window.location.href = url;
    },
    hover() {
      this.$emit('hover');
    },
    leave() {
      this.$emit('leave');
    },
  },
};
</script>

<style lang="scss" scoped>
  @import '../../../../assets/css/global';
  .carousel-expand-menu {
    height: 100%;
    position: absolute;
    top: 0;
    left: 234px;
    background: white;
    box-sizing: border-box;
    border: 1px solid $shadow-color;
    box-shadow: 5px 5px 15px $shadow-color;
  }
  .carousel-expand-menu ul {
    font-size: 0;
    padding: 2px 1px;
  }
  .ca-expand-item {
    width: 251px;
    height: 76px;
    display: inline-block;
    position: absolute;
  }
  .ca-expand-item:hover {
    color: $mi-orange;
    cursor: pointer;
  }
  .ca-expand-item-img {
    display: inline-block;
    height: 40px;
    width: 40px;
    vertical-align: middle;
    transform: translateY(-4px);
    margin: 0 10px;
  }
  .ca-expand-item-desc {
    font-size: 14px;
    line-height: 76px;
  }
</style>
