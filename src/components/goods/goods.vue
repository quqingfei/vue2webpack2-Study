<template>
<div class="goods">
  <div class="menu-wrapper">
    <ul>
      <li v-for="item in goods" class="menu-item">
        <span class="text">
          <span v-show="item.type>0" class="icon" :class="classMap[item.type]"></span>{{item.name}}
        </span>
      </li>
    </ul>
  </div>
  <div class="foods-rwrapper"></div>
</div>
	
</template>

<script>
	export default {
    props: {
      seller: {
        type: Object
      }
    },
    data() {
      return {
        goods: []
      };
    },
    created() {
      this.classMap = ['decrease', 'discount', 'special', 'invoice', 'uarantee'];
      this.$http.get('/api/goods').then(response => {
          if(response.body.error === 0){
            this.goods = response.body.data;
          };
        }, response => {
      });
    }
  };
</script>

<style lang="stylus" rel="stylesheet/stylus" scoped>
@import "../../common/stylus/mixin.styl"
.goods
  position absolute
  top 176px
  bottom 46px
  display flex
  width 100%
  overflow hidden
  .menu-wrapper
    flex 0 0 80px
    width 80px
    background-color #f3f5f7
    .menu-item
      display table
      width 56px
      height 54px
      line-height 14px
      margin 0 auto
      .text
        display table-cell
        vertical-align middle
        border-1px(rgba(7,17,27,0.2))
        font-size 12px
      .icon
        vertical-align top
        display inline-block
        width 12px
        height 12px
        margin-right 2px
        background-size 12px 12px
        background-repeat no-repeat
        &.decrease
          bg-image('decrease_3')
        &.discount
          bg-image('discount_3')
        &.guarantee
          bg-image('guarantee_3')
        &.invoice
          bg-image('invoice_3')
        &.special
          bg-image('special_3')
  .foods-rwrapper
    flex 1
</style>
