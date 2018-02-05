<template>
  <div class="star-board">
    <star-nav></star-nav>
    <star-product-adv></star-product-adv>
  </div>
</template>

<script>
import StarNav from './StarBoardComp/StarNav';
import StarProductAdv from './StarBoardComp/StarProductAdv';

export default {
  name: 'star-board',
  components: {
    StarNav,
    StarProductAdv,
  },
};
</script>

<style scoped>
  .star-board {
    font-size: 0;
    width: 100%;
    height: 170px;
    margin-top: 14px;
  }
</style>
