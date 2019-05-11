<template>
  <div class="wrapper">
  <swiper :options="swiperOption">
    <!-- slides -->
    <swiper-slide v-for="item in list" :key="item.id">
      <img class="swiper-img" :src="item.imgUrl">
    </swiper-slide>
    <!-- Optional controls -->
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
</div>
</template>

<script>
    export default {
      name: "Homeswiper",
      props: {
        list:Array
      },
      data(){
          return {
            swiperOption:{
              pagination: '.swiper-pagination',
            }
          }
      }
    }
</script>

<style lang="stylus" scoped>

  .wrapper >>> .swiper-pagination-bullet-active
    /*>>> 样式穿透*/
    background: #fff !important
  .wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 31.25%
    background: #eee
    .swiper-img
      width: 100%

</style>
