<template>
  <div class="search-box" @mouseenter="hover" @mouseleave="unhover">
    <form class="search-form" action="">
      <label for="GET-name"></label>
      <input class="search-input" @focus="focus"
             @blur="blur" id="GET-name" v-model="inputText"
             :class="{'border-type-hov':isHover, 'border-type-act': isActive}"
             autocomplete="off" type="text" name="search-input">
      <input class="search-btn" type="submit" value="">
      <i class="search-btn-icon iconfont" @click="jump(inputText)"
         :class="{'border-type-hov':isHover, 'border-type-act': isActive}">&#xe617;</i>
      <div class="hot-words" :class="{hide: isActive}">
        <a href="https://www.mi.com/redmi5/">小米5 Plus</a>
        <a href="https://www.mi.com/redmi5/">小米Note3</a>
      </div>
      <ul class="res-lis" :class="{hide: !isActive}"
          @mouseenter="hoverList" @mouseleave="unHoverList">
        <li v-for="resTag in resTags" :key="resTag.name" @click="jump(resTag.name)">
          <span>{{ resTag.name }}</span>
          <span class="sub-res-hint">约有{{ resTag.count }}件</span>
        </li>
      </ul>
    </form>
  </div>
</template>

<script>
import axios from 'axios';
import _ from 'lodash';

export default {
  name: 'search-box',
  props: ['initTags'],
  data() {
    return {
      isActive: false,
      isHover: false,
      isHoverList: false,
      inputText: '',
      resTags: Object.assign([], this.initTags),
    };
  },
  watch: {
    inputText() {
      this.getSearchResult();
    },
  },
  methods: {
    getSearchResult: _.debounce(function f() {
      axios.get('http://localhost:3000/search/')
        .then((res) => {
          this.resTags = res.data.result;
        });
    }, 500),
    hover() {
      if (!this.isActive) this.isHover = true;
    },
    unhover() {
      if (!this.isActive) this.isHover = false;
    },
    focus() {
      this.isHover = false;
      this.isActive = true;
    },
    blur() {
      this.isHover = false;
      this.isActive = this.isHoverList;
    },
    hoverList() {
      this.isHoverList = true;
    },
    unHoverList() {
      this.isHoverList = false;
    },
    jump(targetName) {
      window.location.href = `https://search.mi.com/search_${targetName}`;
    },
  },
};
</script>

<style lang="scss" scoped>
  @import '../../assets/css/global';
  $nor-border-color: $shadow-grey;
  $act-border-color: $mi-orange;
  $hov-border-color: #A4A4A4;
  $search-res-hover: #FAFAFA;
  $search-res-hint: #B4B4B4;
  .search-form {
    height: 50px;
    position: relative;
    top: 50%;
    right: 1px;
    transform: translateY(-50%);
    font-size: 0;
  }
  .search-form .hot-words {
    position: absolute;
    right: 55px;
    bottom: 16px;
    font-size: 12px;
  }
  .search-form .hot-words a {
    color: $text-origin-grey;
    background: #EFEFEF;
    padding: 2px 5px;
    margin-right: 3px;
  }
  .search-form .hot-words a:hover {
    background: $mi-orange;
    color: white;
  }
  .search-form input {
    height: 50px;
    vertical-align: middle;
  }

  .search-input {
    width: 245px;
    box-sizing: border-box;
    position: relative;
    border: 1px solid $nor-border-color;
    outline: none;
    padding: 0 12px;
    font-size: 14px;
  }

  .search-btn {
    width: 50px;
    background: white;
    box-sizing: content-box;
    border: none;
  }

  .search-btn-icon {
    font-size: 25px;
    position: absolute;
    box-sizing: border-box;
    right: 0;
    width: 50px;
    height: 50px;
    text-align: center;
    line-height: 50px;
    border: 1px solid $nor-border-color;
    border-left: none;// 去除border重复
  }

  .search-btn-icon:hover {
    background: $act-border-color;
    color: white;
    cursor: pointer;
    border: 1px solid $act-border-color;
  }

  .border-type-act {
    border-color: $act-border-color;
  }
  .border-type-hov {
    border-color: $hov-border-color;
  }

  .res-lis {
    box-sizing: border-box;
    width: 245px;
    border: 1px solid $mi-orange;
    border-top: none;
    background: white;
  }
  .res-lis li {
    position: relative;
    font-size: 12px;
    padding: 0 12px;
    cursor: pointer;
  }
  .res-lis .sub-res-hint {
    color: $search-res-hint;
    float: right;
  }
  .res-lis li span {
    color: black;
    display: inline-block;
    height: 30px;
    line-height: 30px;
  }
  .res-lis li:hover {
    background: $search-res-hover;
  }
  .hide {
    display: none;
  }
</style>
