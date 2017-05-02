<template>
	<div class="header">
    <div class="content-wrapper">
      <div class="avatar">
        <img :src="seller.avatar" height="64" width="64" alt="goods img-head">
      </div>
      <div class="content">
        <div class="title">
          <span class="brand"></span>
          <span class="name">{{seller.name}}</span>
        </div>
        <div class="description">{{seller.description}}/{{seller.deliveryTime}}分钟送达</div>
        <div v-if="seller.supports" class="supports">
          <span class="icon"></span>
          <span class="text">{{seller.supports[0].description}}</span>
        </div>
      </div>
    </div>
    <div class="bulletin-wrapper"></div>
	</div>
</template>

<script>
	export default{
    props: {
      seller: {
        type: Object
      }
    }
	};
</script>

<style lang="stylus" rel="stylesheet/stylus" scoped>
@import "../../common/stylus/mixin.styl" 

  .header
    background-color #000
    color #fff
    .content-wrapper
      padding 24px 12px 18px 24px
      font-size 0
      .avatar
        vertical-align top
        display inline-block
      .content
        display inline-block
        font-size 14px
        margin-left 16px
        .title
          margin 2px 0 8px 0
          .brand
            vertical-align top
            display inline-block
            width 30px
            height 18px
            bg-image('brand')
            background-size 30px 18px
            background-repeat no-repeat
          .name
            margin-left 6px
            font-size 16px
            line-height 18px
            font-weight bold  
</style>
