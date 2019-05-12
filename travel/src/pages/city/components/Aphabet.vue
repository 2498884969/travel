<template>
    <ul class="list">
      <li class="item" v-for="(item, key) in cities" :key="key">{{key}}</li>
    </ul>
</template>

<script>
    export default {
      name: "CityAphabet.",
      props: ['cities']
    }
</script>

<style lang="stylus" scoped>
  @import "~styles/variables"
  .list
    position absolute
    right 0
    top 1.58 rem
    bottom 0
    display flex
    flex-direction column
    justify-content center
    width .4rem
    .item
      height .4rem
      color $bgColor
      text-align center
</style>
