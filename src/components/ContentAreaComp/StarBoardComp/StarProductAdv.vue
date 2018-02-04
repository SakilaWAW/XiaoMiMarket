<template>
  <div class="star-product-adv">
    <ul class="star-adv-container">
      <li class="star-adv" v-for="(starAdv, index) in starAdvList"
         :style="{background: `url(${starAdv.img})`}" :key="index"></li>
    </ul>
  </div>
</template>

<script>
const starAdvImg1 = require('../../../assets/star_adv_1.png');
const starAdvImg2 = require('../../../assets/star_adv_2.png');
const starAdvImg3 = require('../../../assets/star_adv_3.png');

export default {
  name: 'star-product-adv',
  data() {
    return {
      starAdvList: [
        { img: starAdvImg1 },
        { img: starAdvImg2 },
        { img: starAdvImg3 },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
  .star-product-adv {
    display: inline-block;
    height: 100%;
    width: 987px;
    margin-left: 15px;
  }
  .star-adv-container {
    display: flex;
    justify-content: space-between;
    height: 100%;
    width: 100%;
  }
  .star-adv {
    width: 317px;
    height: 100%;
    display: inline-block;
  }
  .star-adv:hover {
    cursor: pointer;
  }
</style>
