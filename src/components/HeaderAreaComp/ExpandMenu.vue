<template>
  <div class="expand-menu">
    <ul class="menu-container">
      <li class="menu-item" v-for="item in items">
        <div>

        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'expand-menu',
  data() {
    return {
      items: [
        { isNew: true, img: '', name: '红米Note3', value: '1233元起' },
        { isNew: true, img: '', name: '小米7', value: '2013元起' },
        { isNew: false, img: '', name: '红米4', value: '1399元起' },
        { isNew: false, img: '', name: '小米Mix2', value: '3999元起' },
        { isNew: false, img: '', name: '小米Mix2', value: '3999元起' },
        { isNew: false, img: '', name: '小米Mix2', value: '3999元起' },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
  @import '../../assets/css/global';
  $menu-height: 230px;
  .expand-menu {
    width: 100%;
    height: $menu-height;
    background: yellowgreen;
  }
  .menu-container {
    display: flex;
    width: $site-content-width;
    height: $menu-height;
    margin: 0 auto;
    background: indianred;
  }

  .menu-item {
    width: 201px;
    margin-right: 5px;
    height: $menu-height;
    background:yellow;
  }
  .menu-item:nth-child(1) {
    margin-left: 5px;
  }
</style>
