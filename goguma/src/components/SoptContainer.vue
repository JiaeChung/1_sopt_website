<template>
<div id="sopt_wrap">
  <!-- 헤더 -->
  <header>
  <page-title id="sopt_title"></page-title>
  <text-box id="main" v-html="main"></text-box>
  <text-box id="wwd" v-text="wwd"></text-box>
  <text-box id="subject" v-text="subject"></text-box>
  <text-box></text-box>
  <text-box></text-box>

  </header>
  <!-- 본문 -->
  <div class="content_container"></div>
  </div>
</template>

<script>
import Title from './Title'
import Textbox from './TextBox'

export default {
    name: 'SoptContainer',
    components: {
    "pageTitle": Title,
    "TextBox": Textbox
    },
    data() {
      return{
      main: 'S.O.P.T 는 <br>Shout Our Passion Together의 약자로, 대학생 연합 동아리입니다.<br> 동아리는 수도권 지역 대학의 대학생들로 구성되어있으며,<br> IT 벤처 창업을 목적으로 하고 있습니다.',
      wwd: 'WHAT WE DO',
      subject: '기획, 디자인, 서버,\n 안드로이드, iOS, 웹프론트엔드',
      seminar: ''
      }
      
    }
}
</script>

<style>
#sopt_wrap{
  background-image: url('../assets/green.png');
  background-repeat: no-repeat;
  background-size: cover;
  height: 100vh;
}

#main,#wwd,#subject{
  color: white;
}
#sopt_title{
  padding-top: 46vh;
  margin-left: 54vw;
}
#main{
  margin-left: 54vw;
  font-size: 1.5rem;
  font-weight: 200;
  line-height: 3vh;
}
#wwd{
  margin-top: 10vh;
  margin-left: 15vw;
  font-size: 2rem;
  font-weight: 700;
}
#subject{
  margin-top: 2.5vh;
  margin-left: 15vw;
  font-size: 3.3rem;
}
</style>