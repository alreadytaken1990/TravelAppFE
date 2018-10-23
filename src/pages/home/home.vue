<template>
  <div class="home">
    <HomeHeader></HomeHeader>
    <HomeSwiper :list="swiperList" ref="HS"></HomeSwiper>
    <HomeIcons :list="iconList" style="padding-top:10px"></HomeIcons>
    <HomeCate :list="cateList"></HomeCate>
    <img :src="thisBanner" style="width:100%;padding-top:10px">
    <HomeRecommend :recommed='recommeds'></HomeRecommend>
    <!-- <HomeWeekend :recommed='recommeds'></HomeWeekend> -->
    <HomeFoorter style="margin-top:5px"></HomeFoorter>
  </div>
</template>

<script>
  import HomeHeader from './components/header'
  import HomeSwiper from './components/swiper'
  import HomeIcons from './components/icons'
  import HomeRecommend from "./components/recommend"
  import HomeWeekend from "./components/weekend"
  import HomeCate from "./components/category"
  import HomeFoorter from "./components/footer"
  import axios from 'axios'
  import icon1 from "@/assets/自由行.png"
  import icon2 from "@/assets/团体行.png"
  import icon3 from "@/assets/租车.png"
  import icon4 from "@/assets/大巴.png"
  import icon5 from "@/assets/pet医学检查.png"
  import swiper1 from "@/assets/lb3.png"
  import swiper2 from "@/assets/lb5.png"
  import swiper3 from "@/assets/lb7.png"
  import swiper4 from "@/assets/lb8.png"
  import linkImg1 from "@/assets/自由行1.png"
  import linkImg2 from "@/assets/团体行1.png"
  import linkImg3 from "@/assets/bus.png"
  import linkImg4 from "@/assets/租车1.png"
  import linkImg5 from "@/assets/医学检查.png"
  import banner from "@/assets/banner.jpg"

  export default {
    name: 'hello',
    data() {
      return {
        thisBanner: banner,
        recommeds: [{
            "id": "0001",
            "imgUrl": linkImg1,
            "title": "自由行",
            "desc": "由旅行社安排住宿与交通，饮食由旅客自行安排。更自由、方便，时间安排可以随意调整，行程上的游览也可以随心意改变。"
          }, {
            "id": "0002",
            "imgUrl": linkImg2,
            "title": "团体行",
            "desc": "旅行社提供线路，游客选择购买，然后游客在规定的时间、地点、景区、在导游的陪同下，乘坐交通工具，住预定的宾馆，按照规定的线路完成食、住、行、游、购、娱等旅游过程。"
          }, {
            "id": "0003",
            "imgUrl":linkImg3,
            "title": "巴士",
            "desc": "日本租大巴车,价格一览,约车租车包车配专业老司机,大巴客车商务车,一站式租车平台,预约租车,专车接送,价格实惠!"
          }, {
            "id": "0004",
            "imgUrl": linkImg4,
            "title": "租车",
            "desc": "提供日本各大城市租车服务，随租随还，方便快捷"
          }, {
            "id": "0005",
            "imgUrl": linkImg5,
            "title": "医学检查",
            "desc": "由日本最专业的医院提供全面的pet医学检查"
          }],
        swiperList:  [{
            "id": "0001",
            "imgUrl": swiper1
          },{
            "id": "0002",
            "imgUrl": swiper2
          },{
            "id": "0003",
            "imgUrl": swiper3
          },{
            "id": "0004",
            "imgUrl": swiper4
          }],
        iconList:[{
            "id": "0001",
            "imgUrl": icon1,
            "desc": "个人行"
          }, {
            "id": "0002",
            "imgUrl": icon2,
            "desc": "团体行"
          }, {
            "id": "0003",
            "imgUrl": icon3,
            "desc": "租车"
          }, {
            "id": "0004",
            "imgUrl": icon4,
            "desc": "大巴"
          }, {
            "id": "0005",
            "imgUrl": icon5,
            "desc": "医学检查"
          }],
        cateList: [{
            "id": "0001",
            "name": "熊野古道",
            "desc": "くまのこどう"
          }, {
            "id": "0002",
            "name": "和歌山城",
            "desc": "わかやまじょう"
          }, {
            "id": "0003",
            "name": "白良滨",
            "desc": "しららはま"
          }, {
            "id": "0004",
            "name": "三段壁",
            "desc": "さんだんべき"
          }, {
            "id": "0005",
            "name": "千层数",
            "desc": "千畳敷"
          },{
            "id": "0006",
            "name": "円月岛",
            "desc": "円月島"
          }, {
            "id": "0007",
            "name": "那智瀑布",
            "desc": "那智滝"
          }, {
            "id": "0008",
            "name": "潮岬",
            "desc": "しおのみさき"
          }
        ]
      }
    },
    methods: {
      getHomeInfo() {
        // 获取本地json
        axios.get('/static/mock/index.json')
          .then(this.getHomeInfoSuss)
      },
      getHomeInfoSuss (res) {
        //this.recommeds = res.data.recommed
        //this.swiperList = res.data.swiperList
        //this.iconList = res.data.iconList
      }
    },
    mounted() {
      this.getHomeInfo()
    },
    components: {
      HomeHeader,
      HomeSwiper,
      HomeIcons,
      HomeRecommend,
      HomeWeekend,
      HomeCate,
      HomeFoorter
    }
  }
</script>

<style>

</style>
