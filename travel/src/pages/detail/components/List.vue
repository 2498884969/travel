<template>
<div>
  <div class="item" v-for="(item, index) in list"
       :key="index">
    <div class="item-title border-bottom">
      <span class="item-title-icon"></span>{{item.title}}
    </div>
    <div v-if="item.children" class="item-children">
      <detail-list :list="item.children"></detail-list>
    </div>
  </div>
</div>
</template>

<script>
    export default {
      name: "DetailList",
      props: {
        list: Array
      }
    }
</script>

<style lang="stylus" scoped>
.item-title
  line-height .8rem
  font-size .32rem
  padding-left: .2 rem
  .item-title-icon
    display: inline-block;
    position: relative;
    width: .36rem;
    height: .36rem;
    top: .1rem;
    left: .06rem;
    background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat;
    margin-right: .1rem;
    background-size: .4rem 3rem;
.item-children
  padding-left .2rem
</style>
