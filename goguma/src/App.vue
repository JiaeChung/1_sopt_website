<template>
  <div id="app">
    <nav>
    <b-progress class="mt-1" :max="max" style="margin-top: 0 !important; background-color: #000000 !important; height: .5rem !important;">
      <b-progress-bar :value="counter" variant="secondary" height="10px"></b-progress-bar>
    </b-progress>
    <ul>
      <li class="first">
        <router-link to="/home" class="menu" @click.native="clickHome">SOPT</router-link>
        <nav-circle v-show="this.$route.path === '/home'||this.$route.path === '/'"></nav-circle>
        </li>
      <li class="second">
        <router-link to="/sopt" class="menu" @click.native="clickSopt">S.O.P.T</router-link>
        <nav-circle v-show="this.$route.path === '/sopt'"></nav-circle>
        </li>
      <li class="third">
        <router-link to="/notice" class="menu" @click.native="clickNotice">Notice</router-link>
        <nav-circle v-show="this.$route.path === '/notice'"></nav-circle>
        </li>
      <li class="fourth">
        <router-link to="/story" class="menu" @click.native="clickStory">Story</router-link>
        <nav-circle v-show="this.$route.path === '/story'"></nav-circle>
        </li>
      <li class="fifth">
        <router-link to="/information" class="menu" @click.native="clickInformation">Information</router-link>
        <nav-circle v-show="this.$route.path === '/information'"></nav-circle>
        </li>
      <li class="sixth">
        <router-link to="/recruit" class="menu" @click.native="clickRecruit">Recruit</router-link>
        <nav-circle v-show="this.$route.path === '/recruit'"></nav-circle>
        </li>
    </ul>
  </nav>
  <transition name="page" mode="out-in">
    <router-view></router-view>
  </transition>
  </div>
</template>

<script>
import '../node_modules/bootstrap/dist/css/bootstrap.css'
import '../node_modules/bootstrap-vue/dist/bootstrap-vue.css'
import bProgress from '../node_modules/bootstrap-vue/es/components/progress/progress'
import NavCircle from './components/NavCircle'
export default {
  name: 'App',
  components: {
    "bProgress": bProgress,
    "navCircle": NavCircle
  },
  data () {
        return {
          max: 100,
          counter: 10
    }
  },
  methods:{
    clickHome () {
      this.counter = 10
    },
    clickSopt () {
      this.counter = 25
    },
    clickNotice () {
      this.counter = 39
    },
    clickStory () {
      this.counter = 53
    },
    clickInformation () {
      this.counter = 68
    },
    clickRecruit () {
      this.counter = 85
    }
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  font-family: 'Noto Sans', sans-serif;
  color: #707070;
}

nav{
  position: absolute;
  top: 0px;
  width: 100vw;
  line-height: 1;
}

ul{
  margin-top: 1vh;
  font-size: 2rem;
  list-style-type: none;
}

.first{
  font-size: 3rem;
  font-weight: 700;
  margin-left: 7vw;
  padding-left: 0;
}

ul li {
  display: inline;
  padding-right: 10vw;
  
}

.sixth{
  padding-right: 0;
}

.menu{
  color: #707070;
  text-decoration: none;
}

.menu:hover,
.menu:visited,
.menu.router-link-active,
.menu.router-link-exact-active {
  color: #ffffff;
  text-decoration: none;
}

.page-enter-active, .page-leave-active {
  transition: opacity .5s, transform .5s;
}
.page-enter {
  opacity: 0;
  transform: translateX(50%);
}
.page-leave-to {
  opacity: 0;
  transform: translateX(-50%);
}

router-view {
  height: 100vh;
  top: 0;
}

</style>
