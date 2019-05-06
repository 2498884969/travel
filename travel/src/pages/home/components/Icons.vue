<template>
  <div class="icons">
    <swiper>
      <swiper-slide v-for="(page,index) in pages" :key="index">
        <div class="icon" v-for="item in page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl">
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>


    </swiper>
  </div>


</template>

<script>
export default {
  name: "HomeIcons",
  data(){
    return {
      iconList: [
        {
          id: '001',
          imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          desc: '热门景点'
        },
        {
          id: '002',
          imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
          desc: '一日游'
        },
        {
          id: '003',
          imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
          desc: '古迹文化'
        },
        {
          id: '004',
          imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/97/02f5043b51b2102.png',
          desc: '牛首山'
        },
        {
          id: '005',
          imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          desc: '热门景点'
        },
        {
          id: '006',
          imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
          desc: '一日游'
        },
        {
          id: '007',
          imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
          desc: '古迹文化'
        },
        {
          id: '008',
          imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/97/02f5043b51b2102.png',
          desc: '牛首山'
        },
        {
          id: '009',
          imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/b71c1387a921ccf9c6edc7e8def3da90.png',
          desc: '红山动物园'
        }
      ]
    }
  },
  computed: {
    pages() {
      const pages = [];
      this.iconList.forEach((item, index)=>{
        const page = Math.floor(index/8);
        if(!pages[page]){
          pages[page] = []
        }
        pages[page].push(item);
      });
      return pages;
    }
  }
};
</script>

<style lang='stylus' scoped>
  @import "~styles/variables"
  @import "~styles/mixins"
.icons >>> .swiper-container
  height: 0;
  padding-bottom: 50%;
.icon
  position: relative
  height: 0;
  padding-bottom: 25%
  width: 25%;
  overflow: hidden;
  float:left;
  .icon-img
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: .44rem
    box-sizing: border-box
    border: .1 rem
    .icon-img-content
      height: 100%;
      display: block;
      margin: 0 auto;
  .icon-desc
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0
    line-height: .44rem
    height: .44 rem
    color: $darkTextColor
    text-align: center
    ellipsis()
</style>
