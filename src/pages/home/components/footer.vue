<template>
  <div>
    <div class="footerBack">
      <div style="padding:0 10px;width:50%">
        <div style="padding:5px 10px;text-align:center">
          <img :src="logo" style="width:65px;">
        </div>
        <h3 class="desc">留言让我们更好</h3>
        <p class="desc2">联系我们</p>
        <p class="desc2">电话：000-00000000</p>
        <p class="desc2">邮件：example@test.com</p>
        <p class="desc2">微博：test</p>
      </div>

    </div>
    <hr class="hr"/>
    <p class="botAlert">All rights reserved @test 使用条例  隐私政策</p>
  </div>
</template>

<script>
  import logo from "@/assets/logo.png"
  import footerBg from "@/assets/footerBg.png"
  export default {
    data() {
      return {
        logo: logo,
        footerBg: footerBg
      }
    },
    computed: {

    },
    components: {

    },
    methods: {},
    watch: {},
    mounted() {

    }
  }
</script>

<style>
  .desc {
    color: #f0f0f0;
    margin-top: 5px;
    text-overflow: ellipsis;
    margin-left: .1rem;
    overflow: hidden;
    padding: 5px;
    text-align: center;
  }
  .desc2 {
    color: #f0f0f0;
    margin-top: 5px;
    text-overflow: ellipsis;
    margin-left: .1rem;
    overflow: hidden;
    padding: 5px;
    text-align: left;
  }
  .hr {
    color: #fff;
    width: 5px;
    margin-top: 5px;
  }
  .footerBack{
    height: auto;
    min-height: 220px;
    width: 100%;
    background: url('~@/assets/footerBg.png') center center no-repeat;
    background-size: 100% auto;
  }
  .botAlert {
    background-color: #5180b7;
    color: #f0f0f0;
    text-overflow: ellipsis;
    overflow: hidden;
    padding: 5px;
    text-align: center;
  }
</style>
