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
          <div class="dial-service">
            <span class="phone">{{ contactParas.phone }}</span>
            <span class="time">{{ contactParas.time }}</span>
            <a class="contact" :href="contactParas.btnHref">
              <i class="iconfont btn-icon">&#xe68c;</i>
              {{ contactParas.btnTxt }}
            </a>
          </div>
        </div>
      </div>
    </div>
    <div class="register-info">
      <div class="container trust-container">
        <img class="trust-logo" :src="trustInfo.img">
        <ul class="trust-nav-list">
          <li v-for="(nav,index) in trustInfo.nav"
              :key="index"
              class="nav-item"
              :class="{'footer-right-line': hasRightSepInFooter(index)}">
            <a :href="nav.href">{{ nav.txt }}</a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
const logo = require('../assets/mi_logo.png');

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
      contactParas: {
        phone: '400-100-5678',
        time: '周一至周日 8:00-18:00 （仅收市话费）',
        btnTxt: '在线客服',
        btnHref: 'https://www.mi.com/service/contact/',
      },
      trustInfo: {
        img: logo,
        nav: [
          { txt: '小米商城', href: 'https://www.mi.com/index.html' },
          { txt: 'MIUI', href: 'https://www.mi.com/index.html' },
          { txt: '米家', href: 'https://www.mi.com/index.html' },
          { txt: '米聊', href: 'https://www.mi.com/index.html' },
          { txt: '多看', href: 'https://www.mi.com/index.html' },
          { txt: '路由器', href: 'https://www.mi.com/index.html' },
          { txt: '米粉卡', href: 'https://www.mi.com/index.html' },
          { txt: '小米天猫店', href: 'https://www.mi.com/index.html' },
          { txt: '隐私政策', href: 'https://www.mi.com/index.html' },
          { txt: '问题反馈', href: 'https://www.mi.com/index.html' },
          { txt: 'Select Region', href: 'https://www.mi.com/index.html' },
        ],
      },
    };
  },
  methods: {
    hasRightLine(idx) {
      return idx !== this.serviceList.length - 1;
    },
    hasRightSepInFooter(idx) {
      return idx !== this.trustInfo.nav.length - 1;
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
    box-sizing: border-box;
    padding: 20px;
    width: 100%;
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
    right: 267px;
    top: 15%;
  }
  .dial-service {
    width: 200px;
    display: inline-block;
    text-align: center;
    margin-left: 30px;
  }
  .phone, .time {
    display: block;
  }
  .phone {
    font-size: 22px;
    color: $mi-orange;
    margin: 10px 0;
  }
  .time {
    font-size: 12px;
    color: $dark-dark-grey;
    padding: 0 30px;
    margin-bottom: 15px;
  }
  .contact {
    display: inline-block;
    color: $mi-orange;
    border: 1px solid $mi-orange;
    font-size: 12px;
    padding: 3px 20px;
  }
  .contact:hover {
    color: white;
    background: $mi-orange;
  }
  .register-info {
    background: $background-grey;
  }
  .trust-container {
    padding: 30px 20px;
    box-sizing: border-box;
  }
  .nav-item {
    display: inline-block;
    font-size: 12px;
    margin-right: 5px;
    position: relative;
    color: $dark-dark-grey;
    vertical-align: middle;
  }
  .footer-right-line::after {
    content: "";
    position: absolute;
    height: 70%;
    top: 15%;
    width: 1px;
    right: -3px;
    background: $dark-dark-grey;
  }
  .nav-item a {
    color: $dark-dark-grey;
  }
  .nav-item a:hover {
    color: $mi-orange;
  }
  .trust-logo {
    float: left;
    margin-right: 10px;
  }
  .trust-nav-list {
    font-size: 0;
  }
</style>
