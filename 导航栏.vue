<template>
    <div class="navbar">
        <p>Watterson</p>
        <ul class="pc">
            <li><a href="http://www.zhuxf.net/">首页</a></li>
            <li><a href="#">选项卡-先生</a>
               <ul>
                   <li><a href="http://www.zhuxf.net/flop/">碧蓝航线翻翻乐</a></li>
                   <a href="http://www.zhuxf.net/visiable/"><li>新冠肺炎疫情图</li></a>
                   <a href=""><li>3</li></a>
               </ul>
            </li>

            <li><a href="http://www.zhuxf.net/photo">照片墙</a></li>
            <li><a href="#">项目</a></li>
            <li><a href="http://watterson365git.github.io">简历</a></li>
        </ul>
        <img src="../assets/img/img_header/more.png" alt="" @click="changeshow()" >


<!--        //移动端菜单滑块-->
        <div class="menu" v-show="showmenu" >
            <ul class="mp">
            <li><a href="http://www.zhuxf.net/">首页</a></li>
            <li><a href="http://www.zhuxf.net/flop/">碧蓝航线翻翻乐(游戏)</a></li>
            <li><a href="http://www.zhuxf.net/photo">照片墙</a></li>
            <li><a href="#">项目</a></li>
            <li><a href="http://watterson365git.github.io">简历</a></li>
            </ul>
        </div>
    </div>
</template>

<script>
    export default {
        name: "headeri",
        data(){
            return{
                showmenu:false
            }
        },
        methods:{
            changeshow(){
                return this.showmenu = !this.showmenu;
            }
        }
    }
</script>

<style scoped>
    *{
        margin: 0;
        padding: 0;
    }

    .navbar{
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 49px;
        background-color: #333;
        box-shadow:0 -2px 2px #000000 ;
    }

    .navbar .pc{
        list-style: none;
    }

    .navbar .pc li{
        line-height: 49px;
        float: left;
        width: 150px;
        height: 49px;
        background-color: #222;
        margin-right: 1px;
        font-size: 16px;
        text-align: center;
    }

    .navbar .pc li:hover{
        color: #ffffff;
        background: rgba(238,82,83,1);
        animation: changeColor 2s infinite;
        animation-delay: 2s;
        /*打开下拉栏一秒后呼吸效果*/
    }
    @keyframes changeColor {
        0%{
            background: #1d84b5}
        50%{
            background: #00cecb}
        100%{
            background: #1d84b5;}

    }

    .navbar .pc li a{
        text-decoration: none;
        color: #efefef;
        display: block;
        text-align: center;
        line-height: 49px;
        font-weight: bold;
        text-transform: uppercase;
    }

    .navbar .pc li ul li{
        display: none;
        width: 220px;
        height: 49px;
        float: initial;
        background:rgba(1,163,164,1);
        font-size: 10px;
        transition:0.5s;
    }

    .navbar .pc li:hover ul li{
        display: block;
        border-top: 1px solid  rgba(72,219,251,0.5);
    }

    .navbar img{
        width: 40px;
        line-height: 49px;
        float: right;
        display: none;
    }

    .navbar p{
        display: none;
    }

    .navbar .menu{
        display: none;
    }
    @media only screen and (max-width: 970px) {

        @import url('https://fonts.googleapis.com/css?family=Ma+Shan+Zheng&display=swap');
        .navbar{
           position: fixed;
        }
        .navbar img{
            padding-top: 5px;
            display:inline-block;
            padding-right: 30px;
        }

        .navbar .pc{
            display: none;
            list-style: none;
        }

        .navbar p{
            color: #efefef;
            font-family: 'Ma Shan Zheng', cursive;
            line-height: 49px;
            padding-left: 25px;
            font-size: x-large;
            display: inline-block;

        }

        .navbar .menu{
            display: block;
            height: 100%;
            width: 85%;
            position: fixed;
            top: 49px;
            right: 0;
            padding-left: 20px;
            background-color: #333333;
            color: #efefef;
            text-align: left;
            line-height: 49px;
            font-size: x-large;


        }

        .navbar .menu .mp li{
            display: block;
            height: 49px;
            list-style: none;

        }
        .navbar .menu .mp a{
            text-decoration: none;
            color: #efefef;

        }



    }

</style>