<template>
    <div style="padding-top:10px">
      <div class="cate" v-for="item in list" :key="item.id">
        <p class="title">{{item.name}}</p>
        <p>{{item.desc}}</p>
      </div>
    </div>
</template>

<script>
  export default {
    props:{
      list:Array
    },
    data() {
      return {

      }
    },
    computed: {

    }
  }
</script>

<style>
  .cate {
    text-align: center;
    width: 25%;
    float: left;
    padding: 0.2rem 0;
    box-shadow:inset 0 0 0.1rem #999;
  }
  .cate>.title {
    color: #333
  }
  .cate>p {
    color: #999;
    margin-top: 5px;
    text-overflow: ellipsis;
    height: .44rem;
    line-height: .44rem;
    margin-left: .1rem;
    overflow: hidden;
  }
</style>
