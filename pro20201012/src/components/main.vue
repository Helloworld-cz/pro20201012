<template>
  <div class="content-box">
    <!-- 车型亮点 -->
    <div class="part1">
      <div class="part1-title"></div>
      <div class="part1-content">
        <div class="content-title">
          <span class="item" v-for="item in 3" :key="item" :class="{'active':item - 1 === part1TitleIndex}" @click="part1TitleClick(item)"></span>
        </div>
        <div class="content-text">
          <a href="https://product.360che.com/s26/6607_66_index.html">
          <div class="banner-wrapper">
            <ul class="part1-banner">
              <li v-for="(item,index) in part1BnnerImg" :key="index">
                <img :src="item" alt="">
              </li>
            </ul>
          </div>
          <p class="banner-text">
            马力全面升级，机箱桥全面达到10万公里长保养；标配50#鞍座，降低自重；邮箱容积升级到1000L双邮箱，续航里程提升；悬置、地盘等10项目轻量化技术应用，降低自重。
          </p>
          </a>
          <div class="banner-btn">
            <span v-for="(item,index) in part1BnnerImg" :key="index" :class="{'active':part1BannerInedx === index}" @click.stop="part1Change(index)"></span>
          </div>
        </div>
      </div>
    </div>
    <!-- 精彩视频 -->
    <div class="part2">
      <div class="part2-title"></div>
      <div class="part2-content">
        <div class="content-text">
          <div class="banner-wrapper">
            <ul class="part2-banner">
              <li v-for="(item,index) in part2BnnerVideo" :key="index">
                <img :src="part2BnnerVideo[index]" alt="">
              </li>
            </ul>
          </div>
          <p class="banner-text">6大提升66项升级 老司机试驾2018款乘龙H7</p>
          <div class="banner-btn">
            <span v-for="(item,index) in part2BnnerVideo" :key="index" class="active"></span>
          </div>
        </div>
      </div>
    </div>
    <!-- 精美车图 -->
    <div class="part3">
      <div class="part3-title"></div>
      <div class="part3-content">
        <div class="content-text">
          <div class="banner-wrapper">
            <ul class="part3-banner">
            </ul>
          </div>
          <div class="part3-prev"></div>
          <div class="part3-next"></div>
        </div>
      </div>
    </div>
    <!-- 精彩文章 -->
    <div class="part4">
      <div class="part4-title"></div>
      <div class="part4-content">
        <div class="content-text">
          <div class="first-art">
            <a href="http://www.360che.com/tech/190114/105698.html">
              <div class="part4-banner">
                <img src="https://img8.kcimg.cn/HW_Image/2019/1216/1216145248.jpg" alt="">
              </div>
              <h2>315马力带驻车空调 图解新乘龙H7小三桥</h2>
              <p>现如今，中国的电商物流发展速度是全世界最快的，中国也是全世界最大的电商物流市场。快递，已经成为不少卡车司机的固定货源，而国内最适合跑快递的车除了厢式半挂车外，就属9米6的前四后四载货车了。</p>
            </a>
          </div>
          <div class="other-art">
            <div v-for="(item,index) in artic" :key="index" class="arcItem">
              <a href="#">
                <img :src="item.img" alt="">
                <div>
                  <p>{{ item.title }}</p>
                  <p>{{ item.txt }}</p>
                </div>
              </a>

            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      allPart1Img: [
        ['https://img8.kcimg.cn/HW_Image/2019/1218/1218151005.jpg',
          'https://img8.kcimg.cn/HW_Image/2019/1218/1218151022.jpg'],
        ['https://img8.kcimg.cn/HW_Image/2019/1218/1218151100.jpg',
          'https://img8.kcimg.cn/HW_Image/2019/1218/1218151100.jpg'],
        ['https://img8.kcimg.cn/HW_Image/2019/1218/1218151119.jpg',
          'https://img8.kcimg.cn/HW_Image/2019/1218/1218151119.jpg']
      ],
      part1BnnerImg: ['https://img8.kcimg.cn/HW_Image/2019/1218/1218151005.jpg', 'https://img8.kcimg.cn/HW_Image/2019/1218/1218151022.jpg'],
      part1TitleIndex: 0,
      part1BannerInedx: 0,
      part1Timer: null,
      part2BnnerVideo: ['https://4-img.bokecc.com/comimage/9F4E8DB5BE95FD0F/2019-12-12/7E900D9F8A21D8D39C33DC5901307461-1.jpg', 'https://4-img.bokecc.com/comimage/9F4E8DB5BE95FD0F/2019-12-12/7E900D9F8A21D8D39C33DC5901307461-1.jpg', 'https://4-img.bokecc.com/comimage/9F4E8DB5BE95FD0F/2019-12-12/7E900D9F8A21D8D39C33DC5901307461-1.jpg'],
      part3BannerImg: ['https://img8.kcimg.cn/HW_Image/2019/1216/1216145007.jpg', 'https://img8.kcimg.cn/HW_Image/2019/1216/1216145007.jpg', 'https://img8.kcimg.cn/HW_Image/2019/1216/1216145007.jpg'],
      artic: [{
        'img': 'https://img8.kcimg.cn/HW_Image/2019/1216/1216145351.jpg',
        'title': '新乘龙H7搭520康机 为快递快运保驾护航',
        'txt': '2018年12月20日以“智慧物流 绿色高效”为主题的行业研讨会暨乘龙汽车快递快运新品品鉴会在上海如期举行。上海邮政局副局长周德刚、中国快递协会副秘书长高镇海、中国邮政快递报社副社长阴志华、东风柳汽总经理助理林长波、东风康明斯发动机有限公司营销公司负责人王春光、采埃孚商用车事业部全球大客户负责人杨继红以及当地各物流公司老板莅临现场。'
      }, {
        'img': 'https://img8.kcimg.cn/HW_Image/2019/1216/1216145351.jpg',
        'title': '新乘龙H7搭520康机 为快递快运保驾护航',
        'txt': '2018年12月20日以“智慧物流 绿色高效”为主题的行业研讨会暨乘龙汽车快递快运新品品鉴会在上海如期举行。上海邮政局副局长周德刚、中国快递协会副秘书长高镇海、中国邮政快递报社副社长阴志华、东风柳汽总经理助理林长波、东风康明斯发动机有限公司营销公司负责人王春光、采埃孚商用车事业部全球大客户负责人杨继红以及当地各物流公司老板莅临现场。'
      }, {
        'img': 'https://img8.kcimg.cn/HW_Image/2019/1216/1216145351.jpg',
        'title': '新乘龙H7搭520康机 为快递快运保驾护航',
        'txt': '2018年12月20日以“智慧物流 绿色高效”为主题的行业研讨会暨乘龙汽车快递快运新品品鉴会在上海如期举行。上海邮政局副局长周德刚、中国快递协会副秘书长高镇海、中国邮政快递报社副社长阴志华、东风柳汽总经理助理林长波、东风康明斯发动机有限公司营销公司负责人王春光、采埃孚商用车事业部全球大客户负责人杨继红以及当地各物流公司老板莅临现场。'
      }, {
        'img': 'https://img8.kcimg.cn/HW_Image/2019/1216/1216145351.jpg',
        'title': '新乘龙H7搭520康机 为快递快运保驾护航',
        'txt': '2018年12月20日以“智慧物流 绿色高效”为主题的行业研讨会暨乘龙汽车快递快运新品品鉴会在上海如期举行。上海邮政局副局长周德刚、中国快递协会副秘书长高镇海、中国邮政快递报社副社长阴志华、东风柳汽总经理助理林长波、东风康明斯发动机有限公司营销公司负责人王春光、采埃孚商用车事业部全球大客户负责人杨继红以及当地各物流公司老板莅临现场。'
      }, {
        'img': 'https://img8.kcimg.cn/HW_Image/2019/1216/1216145351.jpg',
        'title': '新乘龙H7搭520康机 为快递快运保驾护航',
        'txt': '2018年12月20日以“智慧物流 绿色高效”为主题的行业研讨会暨乘龙汽车快递快运新品品鉴会在上海如期举行。上海邮政局副局长周德刚、中国快递协会副秘书长高镇海、中国邮政快递报社副社长阴志华、东风柳汽总经理助理林长波、东风康明斯发动机有限公司营销公司负责人王春光、采埃孚商用车事业部全球大客户负责人杨继红以及当地各物流公司老板莅临现场。'
      }]
    }
  },
  methods: {
    part1TitleClick (index) {
      this.part1TitleIndex = index - 1
      this.part1BnnerImg = this.allPart1Img[index - 1]
    },
    part1Banner (el) {
      this.part1Timer = setInterval(function () {
        // console.log(el)
      }, 2000)
      console.log('part1', el)
    },
    part1Change (index) {
      this.part1BannerInedx = index
    }
  },
  computed: {

  },
  mounted () {
    this.part1Banner(this)
  }
}
</script>
<style scoped>
  .content-box{
    position: relative;
    z-index: 2;
    overflow-x: hidden;
  }
  .part1{
    margin-bottom: 40px;
  }
  .part1-title{
    width: 358px;
    height: 111px;
    background: url(../assets/img/style-index.png) no-repeat;
    background-position: -4px -440px;
    margin: 0 auto;
    margin-bottom: 20px;
  }
  .part1-content{
    padding: 0 20px;
  }
  .part1 .content-title{
    width: 100%;
    margin-bottom: 20px;
    padding: 0 50px;
  }
  .part1 .content-title .item{
    display: inline-block;
    width: 175px;
    height: 80px;
    background: url(../assets/img/part2-btn.png) no-repeat 50% 50%;
    background-position: -96px -35px;
    margin-left: 20px;
    transition: all .6s;
  }
  .part1-content .content-title .item:nth-child(2){
    background-position-x: -295px;
  }
  .part1-content .content-title .item:nth-child(3){
    background-position-x: -493px;
  }
  .part1 .content-title .item.active{
    background-position-y: -155px;
  }
  .part1-content .content-text{
    width: 644px;
    height: 605px;
    background: url(../assets/img/part2-bj.png) no-repeat 100% 100%;
    margin: 0 auto;
    position: relative;
  }
  .part1 .content-text a{
    display: block;
    padding: 28px 0 0 40px;
  }
  .part1 .banner-wrapper{
    width: 579px;
    overflow: hidden;
    margin:0;
  }
  .part1-banner{
    width: 1200px;
    height: 387px;
  }
  .part1-banner>li{
    float: left;
  }
  .part1-banner>li img{
    width: 579px;
    height: 387px;
  }
  .part1 .banner-btn{
    position: absolute;
    width: 100%;
    height: 40px;
    line-height: 40px;
    top: 420px;
    z-index: 3;
  }
  .part1 .banner-btn span{
    display: inline-block;
    width: 12px;
    height: 12px;
    border-radius: 50%;
    background-color: #008fd1;
  }
  .part1 .banner-btn span:nth-child(1){
    margin-left: calc(50% - 18px);
  }
  .part1 .banner-btn span:nth-child(2){
    margin-left: 5px;
  }
  .banner-btn span.active{
    background-color: #0ff;
  }
  .banner-text{
    margin-top: 5px;
    color: #0ff;
    font-size: 28px;
    overflow:hidden;
    display:-webkit-box;
    -webkit-line-clamp:2;
    -webkit-box-orient:vertical;
  }
  .part1 .banner-text{
    margin-top: 40px;
  }
  /* part2 */
  .part2{
    margin-bottom: 40px;
  }
  .part2-title{
    width: 358px;
    height: 111px;
    background: url(../assets/img/style-index.png) no-repeat;
    background-position: -4px -325px;
    margin: 0 auto;
    margin-bottom: 20px;
  }

  .part2-content .content-text{
    width: 702px;
    height: 663px;
    background: url(../assets/img/part3-bj.png) no-repeat 50% 50%;
    margin: 0 auto;
    margin-top: -86px;
  }
  .part2 .banner-wrapper{
    position: relative;
    width: 571px;
    overflow: hidden;
    margin:0;
    top:160px;
    left: 60px;
    border-radius: 5px;
  }
  .part2-banner{
    width: 1720px;
    height: 384px;
  }
  .part2-banner>li{
    float: left;
  }
  .part2-banner>li img{
    width: 571px;
    height: 384px;
  }
  .part2 .banner-text{
    /* width: 100%; */
    margin-left: 65px;
    margin-top: 180px;
    -webkit-line-clamp:1;
  }
  .part2 .banner-btn{
    position: relative;
    top: 25px;
    height: 40px;
    line-height: 40px;
  }
  .part2 .banner-btn span{
    display: inline-block;
    width: 12px;
    height: 12px;
    border-radius: 50%;
    background-color: #008fd1;
  }
  .part2 .banner-btn span{
    margin-left: 5px;
  }
  .part2 .banner-btn span:nth-child(1){
    margin-left: calc(50% - 18px);
  }
  /* part3 */
  .part3-title{
    width: 358px;
    height: 111px;
    background: url(../assets/img/style-index.png) no-repeat;
    background-position: -368px -325px;
    margin: 0 auto;
    margin-bottom: 20px;
  }
  .part3-content .content-text{
    width: 702px;
    height: 663px;
    background: url(../assets/img/part4-bj.png) no-repeat 50% 50%;
    margin: 0 auto;
    margin-top: -86px;
    position: relative;
  }
  .part3-prev,.part3-next{
    position: absolute;
    width: 46px;
    height: 117px;
    background-color: #fff;
  }
  .part3-prev{
    background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAC4AAAB1CAMAAAAGLiMxAAABjFBMVEUAAAAWjtIWjtIWjtIWjtIWjtIWjtIWjtIWjtIWjtIWjtIWjtIWjtIWjtIWjtIWjtIWjtIWjtKe4fMWjtJa7P7///8WjtLO//+U//9X6v1Z7P5V6fxi9P9T5/pI3/RL4fZf8f9E2/FN4/dR5vlF3fNP5PiF//8alNV6///K/v/x/f9m+f9c7/9y8P79//+////D/v9h7f6a//+h9/+Q9f72/v/z/v9/8v5q7/5l7v7G//+e//+J//9///92//9y//++/P+4+/+x+v+Z9v+H9P538f7R+P3B9v1a6fxW5vtT4/pQ3/hN2vZJ1PNEzvA/yO06weows+MsrOAnpt0joNsgnNgdmNaj///6/v/q/P9L3PKv//+q//+O///H/v9r/v/j+/+p+f/d+v6K8f5t7Py18Pml7/lp4vNS3fFC2vA+2O+k//+w9v+Z8/7I9/3N9ft85fRe3/I2uuc1uebH///u/P6p9P6F8P7n+v3X+f2I6feU6faO6PZx4/Momte29v6e9P548P6t7vib6/d/p/LiAAAAFHRSTlMAccerKNe7s5+al006FQjoYF/s5xR/HskAAAMISURBVFjD7Zhnc9pAEIbBdnpP5JMRICKBmxKwMcUmvZr0nhhIcwwYSACbNJfYqX88Ino1mczN7Cqjybfs52e4Z+49TrcbCAQHgwHvFRRC7BryjB/9fOeJEHu94mrxyvX7Quzc7xFX1Utztx8LsccbvnDm1GT22jshBvZ5wUciE2/Ui8lbj4TYfdADrpw8MTatXlbujYsdRzzginL83Gn1wtWbD4UYPMDjdkXGptRM+u64OBbk8f4C52fU6dkbDxAagaMiZ5+qrwoIjcSxwMvnky8QGoNjgYlnUmgEbu8pHRrw3yWFRuNSaDQuhUbjf4Z2KMjgcmg0LodG4WRoMk6GJuNkaDJOhibjZGgyToYm42RoQxJOhjbA4wjtvaooQgDnF5iRcLJG/uNOday8XVaq7Qn/Zg3/qqWC5gFPLzq0VQuHPODFYac2zWhIY/FOyqHriViU//VkzqE3KvooL1PYcOhcI2G7sDvThviWEYvDnMCzoOuGraJxMSU/OPRiUzchTuHzrjh2hcY/QuUHxGm8ih3vQpzGa2WHXm9iD2kc4qXVvrjG4a74si0OFQJfQ/grEKdxV7zcgziNd6ECcQbPgP4OcRqvliCOU0vj2pJDp7YhTuMh5JkqmhCncC08uuxuOsRp3KysQGcNAP3res896TWFd4/GEqtItauxuBaOxwxXP8Pg0DFwIvOzJA4dM9ErQz/N4pqtb2xCp8jh0K9jNzsUDh1bvwL9XJLBod/I42ZPUzj0bZ0t6H/hcOxmHXyWxKFv6k2cZSvJ4DgMDfxT5jkc+p9wl7UZHPqVIq6nKo1DP9Fcxx0yx+JaX387B/0Ch0M/b/Wr9JXDsfuv7Wrh8iNwHAbdaLVahm5y31XomzHdrhj71QYfjsb7FWU/w+Dd0vw9f/y/I/lXqv83MP/C5t/vfHcwhe7gsJfeY0HqPbjO5i3Z2fB9E9+V+e/5+I6S71f9dsNkMDJOBEPgUjA+phA+ZhxEMP7nM1Qw/mdLUjA0LgfDT90QjP+ZHj8x5OeR/2ba+Zez1J8W7LoKRdleBwAAAABJRU5ErkJggg==);
    top: 280px;
    left: 45px;
  }
  .part3-next{
    background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAC4AAAB1CAMAAAAGLiMxAAABlVBMVEUAAAAWjtIWjtIWjtIWjtIWjtIWjtIWjtIWjtIWjtIWjtIWjtIWjtIWjtIWjtIWjtIWjtIWjtIWjtKd4fMWjtIWjtIWjtJa7P7///8WjtLO//+U//9X6v1Z7P5V6ftT5/pI3/TL//9b7v9F2/Fg8/9R5vlO4/hM4vby/f/H//90//++/v9e8f9C2/EalNWE//9P5fhK4PWY9f9h7f6j//+a//9i9P+G8/5d7P5F3fP7//+J//9/8v538f5l7v7T+P3C9vye//9///95///4/v/1/v/D/f+5+/+x+v+h+P9l9/9j9f/q/P6Q9f5w8P5q7/7M9/1a6fxW5vtT4/pQ3/hN2vZJ1PNEzvA/yO06weows+MsrOAnpt0joNsgm9gcmNbk+/+q+P9L3PKw//+q//+O//98//9r/v9o+v/c+v6K8f5z7v0+2O/C///B///u/P6z9v6i9P6n8/1q7f2z8Pmp7viN6fdw4/No4fJR3fE2uuc1ueaQ8v5t7Pyf7fiU6faC5vV75fRg3/Iomte68fla3vJV3vGwtmSTAAAAF3RSTlMAmXHHq9e6s59MOgfo52AoJxYV7F8sXn5XilIAAAMQSURBVFjD7djpU9pAGAZwi/a+Dxs3JoBGEA9UQKugIm2lJ23tfbdKT6GtIirQqlV7/N3dZN/4ZWfyLJN+9P38m51n9tmB7LaoT6AtoI7PHGaMKfsDjL19+uu8Gj52iLEXD8ZzuurSb57cu6HrKvxoK2M/7t/p6pscxfz4EcZeP757XR+92tMJ+cWDbOj5RLLr6+Stbg3xc22MvXo0PaBf7u/RNMQDJ9nQs9RNfWD4drfmcFDMy4dT1/Sx/kFuHQ6KyS7o765c4pI4KKav68OnQQ1yt5j3H2lp4qCYz90kiYNiuAH8glvMMC9G4p7FSBwUI3GPYgCXipE5KEbiXsXIHBQjcbkYwKViPLhUDODtUjGevFUqxpMzpml6HxWjyMdoaUXeqe1zwBcyMT75WFKJm9nFDmdi0yrcCG4uCT+fwtw0QtH1DjG5CYXVQ73pVcEzSZUw0XBxRvjZMuC0fD0v/EwWctOIJCw3/jLi3AdHwtZv8huAU/zGvOBLZcBFfKs2S/ERp/hbFGcFcYqfI18CXMRPNwqCFzYhN+34OxR/bgJxHieSiK+58RGn+HN0GMYh1/jRTO+68auAU/ztDorvyeX4FcTpLLvxS4DTWa5lhF80ARfx97o1IOfxV0hvjQRNyLVxijJXjCrwqnvq/4QVVjfdbdmxekM4e4WCr8UTkaCJ+JT7e2A5UQBPUfDCbjrKoyDu7vi2HdxEPEl6VQQHvOwGL4ajQUMDPLUodL6etvcQ8WWKsm71RgwT8Y294M4eAl6O0an9K4IDPiN0pi7KB9wN/tNK8OCIl+jU5opOcMCrBaHnG2k7OOBZCp6vifIBr2RizlBwwO0fu/gXPrTj+H81HLeHdhz/ayfCfBJRCo7+hkMRe0JB0iC7QUMacB/fkfgr9f9/A7efaOoLu+VsU9/vfE7R7eCbx+0A3D3wzea7dLNRujf1AA5uZb7vfDSnlW+UNAGpNC8ulQa4V2n+b/JyaZDLpfl44/D/giKXBrhcGuBSaYDLpQEO38VAaaO+3vTwi6Gv90hQGgs0+Zb6DwiE8Hc0UTk8AAAAAElFTkSuQmCC);
    top: 280px;
    right: 45px;
  }
  /* part4 */
  .part4-title{
    width: 358px;
    height: 111px;
    background: url(../assets/img/style-index.png) no-repeat;
    background-position: -4px -555px;
    margin: 0 auto;
    margin-bottom: 20px;
  }
  .part4-content .content-text .first-art{
    margin: 0 auto 30px;
    width: 715px;
    height: 650px;
    background: url(https://s.kcimg.cn/topic/images/dragon-h7/part5-swiperbj.png);
    padding-top: 20px;
    box-sizing: border-box;
  }
  .part4-banner{
    width: 670px;
    height: 440px;
    margin: 0 auto;
  }
  .first-art h2{
    width: 660px;
    height: 32px;
    font-size: 32px;
    font-weight: 700;
    color: #71ffff;
    line-height: 32px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    margin-top: 16px;
    margin-left: 20px;
    box-sizing: border-box;
  }
  .first-art p{
    width: 672px;
    height: 76px;
    font-size: 28px;
    color: #008fd1;
    line-height: 42px;
    margin-top: 9px;
    margin-left: 20px;
    overflow: hidden;
    text-overflow: ellipsis;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    white-space: normal;
    box-sizing: border-box;
  }
  .other-art{
    width: 715px;
    height: 650px;
    margin: 0 auto;
  }
  .other-art .arcItem{
    width: 100%;
    height: 225px;
    background-image: url(https://s.kcimg.cn/topic/images/dragon-h7/style-index.png);
    background-position: -4px -4px;
    background-repeat: no-repeat;
    margin-bottom: 30px;
    box-sizing: border-box;
    padding: 53px 0 0 24px;
    display: block;

  }
  .arcItem img{
    /* position: absolute; */
    display: inline-block;
  }
  .arcItem div{
    float: right;
    width: 60%;
    margin-right: 15px;
  }
  .arcItem div p{
    overflow:hidden;
    display:-webkit-box;
    -webkit-line-clamp:2;
    -webkit-box-orient:vertical;
  }
  .arcItem div p:nth-child(1){
    width: 100%;
    font-size: 28px;
    font-weight: 700;
    color: #71ffff;
    line-height: 36px;
    display: -webkit-box;
    margin-bottom: 9px;
  }
  .arcItem div p:nth-child(2){
    width: 424px;
    font-size: 24px;
    color: rgba(113,255,255,.6);
    line-height: 32px;
    display: -webkit-box;
  }
</style>
