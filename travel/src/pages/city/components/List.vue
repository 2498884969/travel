<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
        </div>
      </div>

      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper" v-for="item in hot" :key="item.id">
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>

      <div class="area" v-for="(item, key) in cities" :key="key">
        <div class="title">{{key}}</div>
        <div class="item-list">
          <div class="item border-bottom" v-for="(innerItem, index) in item" :key="index">{{innerItem.name}}</div>
        </div>
      </div>
    </div>
  </div>

</template>

<script>

import Bscroll from 'better-scroll'

export default {
  name: "CityList",
  props:['cities', 'hot'],
  mounted(){
    this.scroll = new Bscroll(this.$refs.wrapper);
    console.log(this.cities);
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/variables"

  .border-topbottom:before
    border-color #ccc
  .border-topbottom:after
    border-color #ccc
  .border-bottom:before
    border-color #ccc
  .list
    position absolute
    top 1.58 rem
    right 0
    bottom 0
    left 0
    overflow hidden
    .title
      line-height .54 rem
      background #eee
      color #666
      font-size .26 rem
      padding-left .2rem
    .button-list
      padding .1rem .6rem .1rem .1rem
      overflow hidden
      .button-wrapper
        width 33.33%
        float left
        .button
          margin .1rem
          padding .1rem
          text-align center
          border solid .02rem #ccc
          border-radius .06rem

    .item-list
      .item
        line-height .76 rem
        padding-left .2rem
</style>
