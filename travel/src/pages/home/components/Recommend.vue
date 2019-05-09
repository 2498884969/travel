<template>
  <div>
    <div class="title">热点推荐</div>
    <ul>
      <li class="item" v-for="item in recommendList" :key="item.id">
        <img class="item-img" :src="item.imgUrl" alt="">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
    export default {
        name: "HomeRecommend",
        data(){
          return{
            recommendList: [
              {
                id: '001',
                imgUrl:'http://img1.qunarzz.com/sight/p0/1511/ea/eaf1bdc38aed9e6690.img.jpg_200x200_3032bf56.jpg',
                title: '银杏湖乐园',
                desc: '银杏湖乐园描述银杏湖乐园描述'
              },
              {
                id: '002',
                imgUrl:'http://img1.qunarzz.com/sight/p0/1511/ea/eaf1bdc38aed9e6690.img.jpg_200x200_3032bf56.jpg',
                title: '银杏湖乐园',
                desc: '银杏湖乐园描述银杏湖乐园描述'
              },
              {
                id: '003',
                imgUrl:'http://img1.qunarzz.com/sight/p0/1511/ea/eaf1bdc38aed9e6690.img.jpg_200x200_3032bf56.jpg',
                title: '银杏湖乐园',
                desc: '银杏湖乐园描述银杏湖乐园描述'
              },
              {
                id: '004',
                imgUrl:'http://img1.qunarzz.com/sight/p0/1511/ea/eaf1bdc38aed9e6690.img.jpg_200x200_3032bf56.jpg',
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
  .item
    overflow: hidden
    display: flex
    height: 1.9 rem
    .item-img
      height: 1.7 rem
      width: 1.7 rem
      padding: 0.1 rem
    .item-info
      padding: .1 rem
      flex: 1
      width: 0
      .item-title
        line-height: .54 rem
        font-size: .32 rem
      .item-desc
        line-height: .4 rem
        color: #cacaca
        ellipsis()
      .item-button
        margin-top: .2 rem
        border-radius: .06 rem
        background: #ff9300
        color: #fff
</style>
