<template>
  <div class="mHeader">
    <div class="icon"></div>
    <h1 class="text">live Music</h1>
  </div>
</template>

<script>
export default {}
</script>

<style lang="stylus" type="text/stylus">
  // @import "../../common/stylus/variable.styl"
  @import "../../common/stylus/mixin.styl"
.mHeader
  height: 44px
  text-align: center
  color: gold
  font-size:0
  .icon
    display: inline-block
    width: 30px
    height: 32px
    margin-top: 6px
    margin-right: 9px
    bg-image('logo')
    background-size: 30px 32px
  .text
    display: inline-block
    vertical-align: top
    line-height:44px
    font-size:1.8rem
</style>
