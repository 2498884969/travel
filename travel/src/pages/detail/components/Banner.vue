<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img :src="bannerImg"
           class="banner-img">
      <div class="banner-info">
        <div class="banner-title">{{sightName}}</div>
        <div class="banner-number"><span class="banner-icon iconfont icon-arrow">&#xe617;
        </span>{{this.bannerImgs.length}}</div>
      </div>
    </div>

    <common-gallary :imgs="bannerImgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>

  </div>

</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: "DetailBanner",
  props:['sightName', 'bannerImg','bannerImgs'],
  data(){
    return{
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
