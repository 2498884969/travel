<template>
  <div>
    <div class="search">
      <input type="text"
             class="search-input"
             v-model="keyword"
             placeholder="请输入汉字或拼音">
    </div>
    <div class="search-content" v-show="keyword.length" ref="search">
      <ul>
        <li v-for="item in list"
            class="search-item border-bottom"
            :key="item.id"
        >{{item.name}}</li>
        <li class="search-item border-bottom" v-if="hasNoData">没有找到匹配的数据</li>
      </ul>
    </div>
  </div>

</template>

<script>
  import Bscroll from 'better-scroll'
    export default {
      name: "CitySearch",
      props: ['cities'],
      data(){
        return {
          keyword: '',
          list: [],
          timer: null
        }
      },
      computed:{
        hasNoData(){
          return !this.list.length;
        }
      },
      mounted(){
        this.scroll = new Bscroll(this.$refs.search);
      },
      watch: {
        keyword(){
          if (this.timer){
            clearTimeout(this.timer);
          }
          if(!this.keyword){
            this.list = [];
            return
          }
          this.timer = setTimeout(() => {
            let res = [];
            for(let i in this.cities){
              this.cities[i].forEach((item)=>{
                if (item.spell.indexOf(this.keyword) > -1 || item.name.indexOf(this.keyword) > -1){
                  res.push(item)
                }
              })
            }
            this.list = res;
          } ,100)
        }
      }

    }
</script>

<style lang="stylus" scoped>
  @import "~styles/variables"
  .search
    height .72 rem
    background $bgColor
    padding 0 0.1rem
    .search-input
      height 0.62 rem
      line-height 0.62 rem
      box-sizing border-box
      width 100%
      border-radius 0.06 rem
      text-align center
      color #666
      padding 0 0.2rem
  .search-content
    /*0.72(search) + 0.82(header)*/
    top 1.58rem
    left 0
    right 0
    bottom 0
    position absolute
    overflow hidden
    background #eee
    z-index 100
    .search-item
      line-height .62rem
      color #666
      padding-left 0.2rem
      background white
</style>
