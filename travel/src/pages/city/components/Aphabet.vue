<template>
    <ul class="list">
      <li class="item"
          v-for="item in letters"
          :key="item"
          :ref="item"
          @touchstart="handleTouchStart"
          @touchmove="handleTouchMove"
          @touchend="handleTouchEnd"
          @click="handleLetterClick"
      >{{item}}</li>
    </ul>
</template>

<script>
    export default {
      name: "CityAphabet.",
      props: ['cities'],
      data(){
        return {
          touchStatus: false,
          startY: 0,
          timer: null
        }
      },
      updated(){
        this.startY = this.$refs['A'][0].offsetTop;
      },
      computed: {
        letters() {
          const letters = [];
          for(let i in this.cities){
            letters.push(i);
          }
          return letters;
        }
      },
      methods: {
        handleLetterClick(e){
          this.$emit('change', e.target.innerText);
        },
        handleTouchStart(){
        //  触摸事件
          this.touchStatus = true
        },
        handleTouchMove(e){
        //  offsetTop:返回当前元素的上边界到它的包含元素的上边界的偏移量，以像素为单位。
        //  clientY 事件属性返回当事件被触发时鼠标指针向对于浏览器页面（客户区）的垂直坐标
          if(this.touchStatus){
            if(this.timer){
              clearTimeout(this.timer)
            }
            this.timer = setTimeout(()=>{
              const touchY = e.touches[0].clientY - 79;
              let index =Math.floor((touchY - this.startY) / 20);
              if(index >= 0 && index < this.letters.length){
                this.$emit('change', this.letters[index]);
              }
            },16);
          }
        },
        handleTouchEnd() {
          this.touchStatus = false
        }
      }
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
