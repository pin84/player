<template>
  <div class="recommend">
    <div class="recommend-content">
      <div v-if='recommends.length'  class="slider-wrapper">
        <slider>
          <div v-for='(item,index) in recommends' :key='index'>
            <a :href="item.linkUrl">
              <img :src="item.picUrl">
            </a>
          </div>
        </slider>
      </div>
      <div  class="recommend-list">
        <h1 class="list-title">热门歌单推荐</h1>
        <ul></ul>
      </div>
    </div>
  </div>
</template>

<script>
import { getRecommend } from 'api/recommend.js'
import {ERR_OK} from 'api/config'
import Slider from 'base/slider/slider'

export default {
	data() {
		return {
			recommends: []
		}
	},
  created() {
    this._getRecommend()
    
  },
  methods: {
    _getRecommend() {
      getRecommend().then((res) => {
        console.log(res.data.slider)
        this.recommends = res.data.slider
      })
    }
  },
  components: {
  	Slider
  }

}
</script>

<style lang="stylus" type="text/stylus">
  @import "~common/stylus/variable"
  .recommend
    position: fixed
    width: 100%
    top: 88px
    bottom: 0

  /*background: firebrick*/

  .recommend-content
    height 100%
    overflow: hidden
    .slider-wrapper
      position: relative
      width: 100%
      overflow: hidden
    .recommend-list
      .list-title
        height: 65px
        line-height: 65px
        text-align: center
        font-size: $font-size-medium
        color: $color-theme
</style>
