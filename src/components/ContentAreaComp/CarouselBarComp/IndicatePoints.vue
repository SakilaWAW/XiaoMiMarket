<template>
  <div class="indicate-points">
    <ul class="point-lis">
      <!--<li class="point" v-for=""></li>-->
    </ul>
  </div>
</template>

<script>
export default {
  name: 'indicate-points',
  props: [
    'totalCount',
    'currentCount',
  ],
};
</script>

<style lang="scss" scoped>

</style>
