<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img src="//img1.qunarzz.com/sight/p0/1902/84/84696f368bbec10da3.img.jpg_600x330_5ca3e181.jpg"
           class="banner-img">
      <div class="banner-info">
        <div class="banner-title">北京世界园艺博览会</div>
        <div class="banner-number"><span class="banner-icon iconfont icon-arrow">&#xe617;</span>39</div>
      </div>
    </div>

    <common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>

  </div>

</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: "DetailBanner",
  data(){
    return{
      imgs: ["http://img1.qunarzz.com/sight/p0/1511/ea/eaf1bdc38aed9e6690.img.jpg_r_800x800_ea8baf6d.jpg",
        "http://img1.qunarzz.com/sight/p0/1511/ea/eaf1bdc38aed9e6690.img.jpg_r_800x800_ea8baf6d.jpg"],
      showGallary: false
    }
  },
  methods: {
    handleBannerClick(){
      this.showGallary = true;
    },
    handleGallaryClose(){
      this.showGallary = false;
    }
  },
  components: {
      CommonGallary
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    padding-bottom 55%
    overflow hidden
    height 0
    background #cacaca
    position relative
    .banner-img
      width 100%
    .banner-info
      display flex
      position absolute
      left 0
      right 0
      bottom 0
      line-height .6 rem
      /*background red*/
      background-image linear-gradient(rgba(0,0,0,0),rgba(0,0,0,0.8))
      color white
    .banner-title
      flex 1
      font-size .32 rem
      padding-left .2 rem
    .banner-number
      height .4rem
      line-height .4rem
      padding 0 .4rem
      margin .1rem auto
      border-radius .2rem
      background rgba(0,0,0,.8)
      margin-right .2rem
      font-size .24rem
      .banner-icon
        font-size .24rem

</style>
