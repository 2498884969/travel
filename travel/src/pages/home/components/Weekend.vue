<template>
  <div>
    <div class="title">热点推荐</div>
    <ul>
      <li class="item" v-for="item in list" :key="item.id">
        <div class="item-img-content">
          <img class="item-img" :src="item.imgUrl" alt="">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: "HomeWeekend",
    props: {list:Array},
    data(){
      return{
      }
    }
  }
</script>

<style lang="stylus" scoped>
  @import "~styles/mixins"

  .title
    line-height: .8rem;
    background: #cacaca
    text-indent: .2rem
  .item-img-content
    overflow: hidden
    width: 100%
    padding-bottom: 37.08%
    height: 0
    background #cacaca
    .item-img
      width: 100%
  .item-info
    padding: .1 rem
    .item-title
      line-height: .54 rem
      font-size: .32 rem
    .item-desc
      line-height: .4 rem
      color: #cacaca
      ellipsis()
</style>
