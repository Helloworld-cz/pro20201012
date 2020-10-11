<template>
  <div class="topic-global-footer">
    Copyright &copy; 2009 - {{ nowDate }} 卡车之家 －
    网聚卡车人的力量<span>经营许可证编号：京ICP证080575号/京ICP备09080840号</span>
    <span>{{ a }}</span>
  </div>  
</template>
<script>
export default {
  data(){
    return {
      nowDate:new Date().getFullYear()
    }
  },
  conputed:{
    // nowDate:function(){
    //   return new Date().getFullYear();
    // }
  }
}
</script>
<style scoped>

</style>