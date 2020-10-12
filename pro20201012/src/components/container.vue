<template>
  <div class="container">
    <div class="header">
    </div>
    <conMain />
    <div class="bj1"></div>
    <div class="bj2"></div>
    <div class="bj3"></div>
    <div class="bj4"></div>
    <div class="bj5"></div>
  </div>

</template>
<script>
import conMain from './main.vue'
export default {
  components: {
    conMain
  }
}
</script>
<style scoped>
  .container{
    margin: 0 auto;
  }
  .container .header{
    height: 844px;
    max-width: 1920px;
    margin: 0 auto;
    position: relative;
    background: url(https://s.kcimg.cn/topic/images/dragon-h7/header.png) no-repeat 50% 50%;
  }
  .container .bj1,.container .bj2,.container .bj3,.container .bj4,.container .bj5{
    width: 100%;
    position: absolute;
  }
  .container .bj1{
    top: 844px;
    height: 383px;
    background: url(https://s.kcimg.cn/topic/images/dragon-h7/m-bj1.png) no-repeat 50% 50%;
  }
  .container .bj2{
    top:1226px;
    height: 568px;
    background: url(https://s.kcimg.cn/topic/images/dragon-h7/m-bj2.png) no-repeat 50% 50%;
  }
  .container .bj3{
    top: 1790px;
    height: 748px;
    background: url(https://s.kcimg.cn/topic/images/dragon-h7/m-bj3.png) no-repeat 50% 50%;
  }
  .container .bj4{
    top: 2530px;
    height: 1065px;
    background: url(https://s.kcimg.cn/topic/images/dragon-h7/m-bj4.png) no-repeat 50% 50%;
  }
  .container .bj5{
    top: 3590px;
    height: 1065px;
    background: url(https://s.kcimg.cn/topic/images/dragon-h7/m-bj4.png) no-repeat 50% 50%;
  }
</style>
