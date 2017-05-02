<template>
  <div id="app">
    <v-header></v-header>
    <div class="tab">
      <div class="tab-item">商品</div>
      <div class="tab-item">评价</div>
      <div class="tab-item">商家</div>
    </div>
    <div class="footer">I`m footer</div>
  </div>
</template>

<script>
  import vHeader from './components/header/header';
  export default {
    components: {
      vHeader
    }
  };
</script>

<style lang="stylus" rel="stylesheet/stylus" scoped>
#app
  .tab
    display: flex
    width: 100%
    height: 40px
    line-height: 40px
    .tab-item
      flex: 1
      text-align: center
</style>
