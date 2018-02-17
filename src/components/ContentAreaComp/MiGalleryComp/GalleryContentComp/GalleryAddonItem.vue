<template>
  <div class="gallery-addon-item hover-shadow">
    <div class="container">
      <div class="addon-info">
        <a class="addon-name" :href="addonInfo.url">{{ addonInfo.name }}</a>
        <span class="addon-desc">{{ addonInfo.price }}</span>
      </div>
      <a :href="addonInfo.url"><img class="addon-img" :src="addonInfo.img"></a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'gallery-addon-item',
  props: [
    'addonInfo',
  ],
};
</script>

<style lang="scss" scoped>
  @import "../../../../assets/css/global";
  .container {
    padding-left: 30px;
    position: relative;
    top: 50%;
    transform: translateY(-50%);
  }

  .addon-name {
    display: block;
    color: black;
    text-overflow: ellipsis;
    overflow: hidden;
    white-space: nowrap;
  }
  .addon-desc {
    color: $mi-orange;
  }
  .addon-info {
    height: 42px;
    width: 94px;
  }
  .addon-info, .addon-img {
    display: inline-block;
  }
  .addon-img {
    vertical-align: middle;
  }
</style>
