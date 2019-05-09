<template>
  <div>
    <div class="title">热点推荐</div>
    <ul>
      <li class="item" v-for="item in recommendList" :key="item.id">
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
    data(){
      return{
        recommendList: [
          {
            id: '001',
            imgUrl:'https://imgs.qunarzz.com/sight/source/1603/6d/2f67ae0659f41f.jpg_r_640x214_bf6cbd0b.jpg',
            title: '银杏湖乐园',
            desc: '银杏湖乐园描述银杏湖乐园描述'
          },
          {
            id: '002',
            imgUrl:'https://imgs.qunarzz.com/sight/source/1603/6d/2f67ae0659f41f.jpg_r_640x214_bf6cbd0b.jpg',
            title: '银杏湖乐园',
            desc: '银杏湖乐园描述银杏湖乐园描述'
          },
          {
            id: '003',
            imgUrl:'https://imgs.qunarzz.com/sight/source/1603/6d/2f67ae0659f41f.jpg_r_640x214_bf6cbd0b.jpg',
            title: '银杏湖乐园',
            desc: '银杏湖乐园描述银杏湖乐园描述'
          },
          {
            id: '004',
            imgUrl:'https://imgs.qunarzz.com/sight/source/1603/6d/2f67ae0659f41f.jpg_r_640x214_bf6cbd0b.jpg',
            title: '银杏湖乐园',
            desc: '银杏湖乐园描述银杏湖乐园描述'
          },
        ]
      }
    }
  }
</script>

<style lang="stylus" scoped>
  @import "~styles/mixins"

  .title
    margin-top: .2rem;
    line-height: .8rem;
    background: #cacaca
    text-indent: .2rem
  .item-img-content
    overflow: hidden
    width: 100%
    padding-bottom: 38.93%
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
