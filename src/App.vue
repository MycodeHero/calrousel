<template>
  <div id="calrousel">
    <div class="cal-list" ref="list">
      <item v-for="(imgSrc, index) in imgList" :key="index">
        <img :src="imgSrc"/>
      </item>
    </div>
  </div>
</template>

<script>
  // import arrow from './components/Arrow.vue'
  import item from './components/Item.vue'
  export default {
    name: 'app',
    data () {
      return {
        imgList: ['./static/1.jpg','./static/2.jpg','./static/3.jpg','./static/4.jpg', './static/1.jpg']
      }
    },
    components: {
      item
    },
    mounted () {
      this.$nextTick(this.changePic)
    },
    methods: {
      changePic () {
        let Dom = this.$refs.list
        let count = 0
        setInterval(()=>{
          Dom.style.transition = 'left 0.8s linear'
          Dom.style.left= -205 * count + "px" 
          if(count > 4 && count != 0){
            Dom.style.transition = 'left 0s linear'
            count = 0;
            Dom.style.left = '0px'
            return 
          }
          ++ count
        }, 2000)
      }
    }
  }
</script>

<style>
  #calrousel{
    position:relative;
    margin:100px auto;
    width:200px;
    height:267px;
    overflow:hidden;
    padding:5px;
    border:3px dotted deeppink;
  }
  .cal-list{
    position:absolute;
    left:0px;
    width:1025px;
    display:inline-block;
  }
</style>