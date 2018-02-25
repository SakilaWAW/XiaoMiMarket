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
          <div class="service-col"
               v-for="(service, index) in serviceNavList"
               :key="index">
            <span class="service-title">{{ service.title }}</span>
            <ul>
              <li class="service-item"
                  v-for="(item, index) in service.items"
                  :key="index">
                <a class="item-txt" :href="item.href">{{ item.txt }}</a>
              </li>
            </ul>
          </div>
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
      serviceNavList: [
        {
          title: '帮助中心',
          items: [
            { txt: '账户管理', href: 'https://www.mi.com/service/account/register/' },
            { txt: '购物指南', href: 'https://www.mi.com/service/account/register/' },
            { txt: '订单操作', href: 'https://www.mi.com/service/account/register/' },
          ],
        },
        {
          title: '服务支持',
          items: [
            { txt: '售后政策', href: 'https://www.mi.com/service/account/register/' },
            { txt: '自助服务', href: 'https://www.mi.com/service/account/register/' },
            { txt: '相关下载', href: 'https://www.mi.com/service/account/register/' },
          ],
        },
        {
          title: '线下门店',
          items: [
            { txt: '小米之家', href: 'https://www.mi.com/service/account/register/' },
            { txt: '服务网点', href: 'https://www.mi.com/service/account/register/' },
            { txt: '零售网点', href: 'https://www.mi.com/service/account/register/' },
          ],
        },
        {
          title: '关于小米',
          items: [
            { txt: '了解小米', href: 'https://www.mi.com/service/account/register/' },
            { txt: '加入小米', href: 'https://www.mi.com/service/account/register/' },
            { txt: '联系我们', href: 'https://www.mi.com/service/account/register/' },
          ],
        },
        {
          title: '关注我们',
          items: [
            { txt: '新浪微博', href: 'https://www.mi.com/service/account/register/' },
            { txt: '小米部落', href: 'https://www.mi.com/service/account/register/' },
            { txt: '官方微信', href: 'https://www.mi.com/service/account/register/' },
          ],
        },
        {
          title: '特色服务',
          items: [
            { txt: 'F码通道', href: 'https://www.mi.com/service/account/register/' },
            { txt: '礼物码', href: 'https://www.mi.com/service/account/register/' },
            { txt: '防伪查询', href: 'https://www.mi.com/service/account/register/' },
          ],
        },
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
    font-size: 0;
    width: 100%;
  }
  .service-list {
    width: 100%;
    height: 80px;
    font-size: 0;
    display: flex;
    justify-content: space-around;
    border-bottom: 1px solid $shadow-grey;
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
    height: 30%;
    width: 1px;
    top: 30%;
    right: -60px;
    background: $shadow-grey;
  }
  .service-nav, .dial-service, .service-col {
    display: inline-block;
  }
  .service-title {
    display: inline-block;
    font-size: 16px;
    margin-bottom: 20px;
  }
  .item-txt {
    display: inline-block;
    font-size: 12px;
    color: $dark-dark-grey;
    margin-bottom: 10px;
  }
  .item-txt:hover {
    color: $mi-orange;
  }
  .service-nav {
    padding: 20px;
    width: 880px;
    display: flex;
    justify-content: space-between;
    position: relative;
  }
  .service-nav::after {
    content: "";
    height: 70%;
    width: 1px;
    background: $shadow-grey;
    position: absolute;
    right: -51px;
    top: 15%;
  }
</style>
