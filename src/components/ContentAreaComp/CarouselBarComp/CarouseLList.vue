<template>
  <div class="carousel-l-list">
    <ul class="link-lis">
      <li v-for="(menu, index)  in menuMap" :key="index"
          @mouseenter="hover(index)" @mouseleave="unhover()" @click="jumpTo(menu.href)">
        <span>{{ menu.name }}</span>
        <i class="iconfont carousel-link-lis-r-arrow">&#xe612;</i>
      </li>
    </ul>
    <carousel-expand-menu :menuData="curData" v-show="isExpand"
                          @hover="hover" @leave="unhover"></carousel-expand-menu>
  </div>
</template>

<script>
import CarouselExpandMenu from './CarouseLListComp/CarouselExpandMenu';

const sPhone = require('../../../assets/s_phone.png');

export default {
  name: 'carousel-l-list',
  components: {
    CarouselExpandMenu,
  },
  data() {
    return {
      curMenuIdx: 0,
      isExpand: false,
      menuMap: [
        {
          name: '手机 电话卡',
          paras: [
            { img: sPhone, desTxt: '小米 Note3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '红米3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Mix2', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3C', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3A', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 NoteX', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note4', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note5', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '红米3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Mix2', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3C', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3A', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 NoteX', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note4', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note5', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
          ],
          href: 'https://www.mi.com/p/1915.html',
        },
        {
          name: '电视 盒子',
          paras: [
            { img: sPhone, desTxt: '小米 Note3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '红米3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Mix2', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3C', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3A', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 NoteX', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note4', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note5', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Mix2', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3C', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3A', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 NoteX', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note4', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note5', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
          ],
          href: 'https://www.mi.com/p/1915.html',
        },
        {
          name: '笔记本',
          paras: [
            { img: sPhone, desTxt: '小米 Note3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '红米3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Mix2', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3C', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3A', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 NoteX', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note4', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note5', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Mix2', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3C', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3A', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 NoteX', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note4', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note5', href: 'https://www.mi.com/mibookair/' },
          ],
          href: 'https://www.mi.com/p/1915.html',
        },
        {
          name: '智能 家电',
          paras: [
            { img: sPhone, desTxt: '小米 Note3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '红米3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Mix2', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3C', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3A', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Mix2', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3C', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3A', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 NoteX', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note4', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note5', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
          ],
          href: 'https://www.mi.com/p/1915.html',
        },
        {
          name: '健康 家具',
          paras: [
            { img: sPhone, desTxt: '小米 Note3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '红米3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Mix2', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3C', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3A', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 NoteX', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note4', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note5', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
          ],
          href: 'https://www.mi.com/p/1915.html',
        },
        {
          name: '出行 儿童',
          paras: [
            { img: sPhone, desTxt: '小米 Note3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '红米3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Mix2', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3C', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3A', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 NoteX', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note4', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note5', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3C', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3A', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 NoteX', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note4', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note5', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
          ],
          href: 'https://www.mi.com/p/1915.html',
        },
        {
          name: '路由器 手机配件',
          paras: [
            { img: sPhone, desTxt: '小米 Note3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '红米3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Mix2', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3C', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3A', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 NoteX', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note4', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note5', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note5', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
          ],
          href: 'https://www.mi.com/p/1915.html',
        },
        {
          name: '移动电源 插线版',
          paras: [
            { img: sPhone, desTxt: '小米 Note3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '红米3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Mix2', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3C', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3A', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 NoteX', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note4', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note5', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
          ],
          href: 'https://www.mi.com/p/1915.html',
        },
        {
          name: '耳机 音响',
          paras: [
            { img: sPhone, desTxt: '小米 Note3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '红米3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Mix2', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3C', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3A', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 NoteX', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note4', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note5', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '红米3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Mix2', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3C', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3A', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 NoteX', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note4', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note5', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
          ],
          href: 'https://www.mi.com/p/1915.html',
        },
        {
          name: '生活 米兔',
          paras: [
            { img: sPhone, desTxt: '小米 Note3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '红米3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Mix2', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3C', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3A', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 NoteX', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note4', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note5', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '红米3', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Mix2', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3C', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米路由器3A', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 NoteX', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note4', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '小米 Note5', href: 'https://www.mi.com/mibookair/' },
            { img: sPhone, desTxt: '笔记本Air 13.3"四核增强', href: 'https://www.mi.com/mibookair/' },
          ],
          href: 'https://www.mi.com/p/1915.html',
        },
      ],
    };
  },
  computed: {
    curData() {
      return this.menuMap[this.curMenuIdx].paras;
    },
  },
  methods: {
    hover(idx) {
      if (idx !== undefined) this.curMenuIdx = idx;
      this.isExpand = true;
    },
    unhover() {
      this.isExpand = false;
    },
    jumpTo(url) {
      window.location.href = url;
    },
  },
};
</script>

<style lang="scss" scoped>
  @import '../../../assets/css/global';
  .carousel-l-list {
    height: 100%;
    width: 234px;
    background: rgba(0,0,0,0.5);
    position: absolute;
    z-index: 1;
  }
  .link-lis {
    padding: 20px 0;
  }
  .link-lis li {
    font-size: 14px;
    color: white;
    padding-left: 30px;
    height: 42px;
    line-height: 42px;
  }
  .link-lis li:hover {
    background: $mi-orange;
    cursor: pointer;
  }
  .carousel-link-lis-r-arrow {
    float: right;
    margin-right: 25px;
  }
</style>
