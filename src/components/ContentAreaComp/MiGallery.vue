<template>
  <div class="mi-gallery">
    <div class="gallery-header">
      <span class="gallery-title">{{ title }}</span>
      <gallery-nav :currentIdx="currentIdx" @pageTo="switchToPage"></gallery-nav>
    </div>
    <gallery-content :dataMap="dataList"></gallery-content>
  </div>
</template>

<script>
import GalleryNav from './MiGalleryComp/GalleryNav';
import GalleryContent from './MiGalleryComp/GalleryContent';

const leftItem = require('../../assets/left-item.png');
const starProduct150 = require('../../assets/star_product150.png');

export default {
  name: 'mi-gallery',
  props: [
    'title',
  ],
  components: {
    GalleryNav,
    GalleryContent,
  },
  data() {
    return {
      currentIdx: 0,
      dataList: {
        leftBar: [
          { img: leftItem, href: 'https://www.mi.com/scooter/' },
        ],
        items: [
          [
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
          ],
          [
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
          ],
          [
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
          ],
          [
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
            { topDesc: '新品', img: starProduct150, name: '小米笔记本Air13.3英寸', subDesc: '极致轻奢，为所欲为', price: '1122元', comment: '感觉不错，手感超级棒。做工精美，，，电脑刚开机，性能...', author: '来自于 李业兴 的评价' },
          ],
        ],
      },
    };
  },
  computed: {
    currentContent() {
      return this.dataList.items[this.currentIdx];
    },
  },
  methods: {
    switchToPage(idx) {
      this.currentPage = idx;
    },
  },
};
</script>

<style lang="scss" scoped>
  @import '../../assets/css/global';
  .gallery-header {
    height: 58px;
    position: relative;
  }
  .gallery-title {
    font-size: 22px;
  }
</style>
