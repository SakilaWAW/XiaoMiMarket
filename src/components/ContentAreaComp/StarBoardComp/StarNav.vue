<template>
  <div class="star-nav">
    <ul class="star-nav-lis">
      <li v-for="(entrance, index) in entranceList" :key="index" @click="jumpTo(entrance.href)"
          :class="{'right-sep-line': hasRightSep(index), 'bottom-sep-line': hasBottomSep(index)}">
        <i class="iconfont e-image" v-html="entrance.fontCode"></i>
        <span class="e-txt">{{ entrance.txt }}</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'star-nav',
  data() {
    return {
      entranceList: [
        { fontCode: '&#xe693;', txt: '选购手机', href: 'https://www.mi.com/compare/' },
        { fontCode: '&#xe693;', txt: '企业团购', href: 'https://www.mi.com/compare/' },
        { fontCode: '&#xe693;', txt: 'F码通道', href: 'https://www.mi.com/compare/' },
        { fontCode: '&#xe693;', txt: '米粉卡', href: 'https://www.mi.com/compare/' },
        { fontCode: '&#xe693;', txt: '以旧换新', href: 'https://www.mi.com/compare/' },
        { fontCode: '&#xe693;', txt: '话费充值', href: 'https://www.mi.com/compare/' },
      ],
    };
  },
  methods: {
    jumpTo(url) {
      window.location.href = url;
    },
    hasRightSep(idx) {
      return idx % 3 < 2;
    },
    hasBottomSep(idx) {
      return idx < 3;
    },
  },
};
</script>

<style lang="scss" scoped>
  @import '../../../assets/css/global';
  $background-grey: #5F5750;
  .star-nav {
    display: inline-block;
    width: 234px;
    height: 100%;
    padding: 3px;
    box-sizing: border-box;
    background: $background-grey;
    vertical-align: top;
  }
  .star-nav-lis li{
    text-align: center;
    color: $dark-dark-grey;
    width: 76px;
    height: 82px;
    box-sizing: border-box;
    display: inline-block;
    padding: 12px 0;
    position: relative;
  }
  .star-nav-lis li:hover {
    color: white;
    cursor: pointer;
  }
  .star-nav-lis .e-image {
    font-size: 30px;
  }
  .e-txt {
    font-size: 12px;
    display: block;
  }
  .right-sep-line::before, .bottom-sep-line::after {
    content: "";
    position: absolute;
    background: rgba(200,200,200,0.05);
  }
  .right-sep-line::before {
    right: 0;
    top: 12px;
    width: 1px;
    height: 58px;
  }
  .bottom-sep-line::after {
    left: 8px;
    bottom: 0;
    width: 60px;
    height: 1px;

  }
</style>
