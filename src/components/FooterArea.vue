<template>
  <div id="footer-area">
    <div class="container">
      <div class="bottom-nav">
        <ul class="service-list">
          <li v-for="(service,idx) in serviceList" :key="idx">
            <a class="service hover-orange-pointer"
               :href="service.href"
               :class="{'right-line': hasRightLine(idx)}">
              <i class="iconfont service-icon" v-html="service.iconFontCode"></i>
              {{ service.txt }}
            </a>
          </li>
        </ul>
        <div class="service-nav">
        </div>
        <div class="dial-service"></div>
      </div>
      <div class="register-info">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'footer-area',
  data() {
    return {
      serviceList: [
        { txt: '预约维修服务', href: 'https://www.mi.com/static/fast/', iconFontCode: '&#xe659;' },
        { txt: '7天无理由退货', href: 'https://www.mi.com/static/fast/', iconFontCode: '&#xe638;' },
        { txt: '15天免费换货', href: 'https://www.mi.com/static/fast/', iconFontCode: '&#xe639;' },
        { txt: '满150元包邮', href: 'https://www.mi.com/static/fast/', iconFontCode: '&#xe64d;' },
        { txt: '520余家售后网店', href: 'https://www.mi.com/static/fast/', iconFontCode: '&#xe609;' },
      ],
    };
  },
  methods: {
    hasRightLine(idx) {
      return idx !== this.serviceList.length - 1;
    },
  },
};
</script>

<style lang="scss" scoped>
  @import '../assets/css/global';
  .container {
    width: $site-content-width;
    margin: 0 auto;
  }
  .bottom-nav {
    background: white;
    width: 100%;
  }
  .service-list {
    width: 100%;
    height: 80px;
    font-size: 0;
    display: flex;
    justify-content: space-around;
    border-bottom: 1px solid #AAA;
  }
  .service {
    line-height: 80px;
    display: inline-block;
    font-size: 16px;
    color: black;
    position: relative;
  }
  .hover-orange-pointer:hover {
    color: $mi-orange;
    cursor: pointer;
  }
  .service-icon {
    font-size: 20px;
  }
  .right-line::after {
    content: "";
    position: absolute;
    height: 20px;
    width: 1px;
    top: 30px;
    right: -60px;
    background: #AAA;
  }
</style>
