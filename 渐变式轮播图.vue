<template>
  <div id="app">
    <div class="wrap">

      <ul class="list">
        <li v-for="(item ,index) in list" class="item" :style="{background:'url('+item.src+') round'}" :class="{active:index===clickindex}">{{item.lable}}</li>
      </ul>

      <ul class="pointlist">
        <a href="#"><li v-for="(item ,index) in list"  @click="topoint(index)" class="point" :class="{pointactive:index===clickindex}"></li></a>
      </ul>

      <a href="#"> <div class="btn" id="btnleft" @click="topre"  > < </div></a>
      <a href="#"><div class="btn" id="btnrigth" @click="tonext"> > </div></a>

    </div>


  </div>
</template>

<script>


export default {
  name: 'App',
  data(){
    return{
      clickindex:1,
      list:[
        {lable:"111111111",src:require( "../1.png")},
        {lable:"222222222",src:require( "../2.png")},
        {lable:"333333333",src:require( "../3.png")},
        {lable:"111111111",src:require( "../1.png")},
        {lable:"222222222",src:require( "../2.png")},
        {lable:"333333333",src:require( "../3.png")},

      ]
    }
  },
  methods:{
    topre(){
      if(this.clickindex ===0){
        return this.clickindex = this.list.length - 1
      }else{
        this.clickindex --
      }

    },
    tonext(){
      if(this.clickindex === this.list.length - 1){
        return this.clickindex = 0
      }else{
        this.clickindex ++
      }
    },
    // 用按钮也可以换页 topoint(index)
    topoint(index){
      this.clickindex = index
    },
    autochange(){
      setInterval(this.tonext,3000)
    }

  },
  created() {
    this.autochange()
  }

}
</script>

<style>

  .wrap{
    padding: 0;
    margin: 0;
    width: 400px;
    height: 250px;
    position: relative;
  }
  .list{
    padding: 0;
    margin: 0;
    width: 400px;
    height: 250px;
    list-style: none;
    /*把item都叠在一起，用position ，子绝父相*/
    position: relative;
  }
  .item{
    width: 100%;
    height: 100%;
    /*这里改变字体大小方便查看item编号*/
    font-weight: bold;font-size: larger; /*把item都叠在一起，用position ，子绝父相*/
    position: absolute;
/*默认透明度为0，在激活后透明度为1，同时添加一个渐变特效*/
    opacity: 0;
    transition: opacity 0.8s;
  }


.btn{
  color: #ffffff;
  background-color: rgba(0,0,0,0.1);
  text-align: center;
  line-height: 40px;
  display: block;
  width: 30px;
  height: 40px;
  position: absolute;
  z-index: 100;
  }

  .btn:hover{
    background-color: rgba(0,0,0,0.4);
  }


  #btnleft{
    left: 0;
    top: 50%;
  margin-top: -30px;
  }

  #btnrigth{
    right: 0;
    top: 50%;
    margin-top: -30px;
  }

  .active{
    z-index: 10;
    opacity: 1;
  }

  .pointlist{
    padding: 0;
    margin: 0;
    position: absolute;
    top: 220px;
    right: 40px;
    z-index: 100;
  }

  .point{
    list-style: none;
    width: 8px;
    height: 8px;
    background-color: rgba(0,0,0,0.4);
    float: left;
    border-radius: 100%;
    margin-right: 10px;
    border:1px solid rgba(255,255,255,.4);
  }

  /*结合clickindex选中而激活的下面的小点*/
  .pointactive{
    background-color: rgba(0,0,0,0.8);
  }
</style>
