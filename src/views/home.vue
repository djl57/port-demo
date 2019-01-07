<template>
  <div>
    <div class="first_view">
      <img :src="firstImg" class="first_img">
      <h1 class="first_view_h1">商标</h1>
      <h2 class="first_view_h2">公司名称</h2>
      <header>
        <nav class="first_view_nav">
          <ul class="first_view_ul">
            <li v-for="(nav, index) in navs" :key="index" class="first_view_li" @click="goto(nav.link)">
              {{ nav.name }}
              <span class="first_view_li_span"></span>
            </li>
          </ul>
        </nav>
      </header>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      firstImg: '',
      // firstImg: require('./../assets/imgs/cover.png'),
      navs: [
        { name: '导航一yi', link: '1', active: false },
        { name: '导航二', link: '2', active: false },
        { name: '导三', link: '3', active: false },
        { name: '导航四四', link: '4', active: false },
        { name: '导航五', link: '5', active: false },
      ]
    }
  },
  methods: {
    goto (link) {
      console.log(link)
    }
  }
}
</script>

<style>
.first_view {
  width: 100%;
  /* 电脑宽度最小算到1024的话这个宽度可以算最小 */
  min-width: 1000px;
  /* height: 100vh就是屏幕的100%高度，就算没有内容也会撑开 */
  height: 100%;
  height: 100vh;
  overflow: hidden;
  overflow-x: hidden;
  overflow-y: hidden;
  position: relative;
  background-color: rgba(0, 0, 0, 0.3);
  background-size: cover;
  font-family: 'KaiTi';
}
.first_img {
  position: fixed;
  z-index: -100;
  object-fit: cover;
  height: 100%;
  /* 设置这两个样式的原因不是很清楚
  left: 50%;
  transform: translateX(-50%); */
}
.first_view_h1 {
  width: 250px;
  height: 30px;
  line-height: 30px;
  text-align: center;
  position: absolute;
  top: 30px;
  left: 30px;
  background-color: #ffffff;
}
@keyframes fadeIn {
  0% { 
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
.first_view_h2 {
  writing-mode: vertical-rl;
  font-feature-settings: "palt";
  color: #fff;
  position: absolute;
  top: 45%;
  right: 50%;
  transform: translateY(-50%);
  animation: fadeIn 7.0s 0.5s;
  animation-fill-mode: both;
  height: 265px;
  font-size: 26px;
  letter-spacing: 0.2em;
}
.first_view_nav {
  overflow: hidden;
  position: absolute;
  bottom: 0;
  right: 5%;
  left: 5%;
  z-index: 200;
  font-size: 24px;
  height: 100px;
}
.first_view_ul {
  display: flex;
  justify-content: space-around;
}
.first_view_li {
  flex: 0 0 1;
  color: #fff;
  letter-spacing: 0.3em;
  font-size: 18px;
  text-align: center;
  line-height: 1.5em;
  position: relative;
}
.first_view_li_span {
  position: absolute;
  left: 0;
  bottom: -6px;
  content: '';
  width: 95%;
  height: 1px;
  background: rgba(255, 255, 255, 0.7);
  transform: scale(0.3, 1);
  transform-origin: center top;
  transition: transform .3s;
}
.first_view_li:hover .first_view_li_span {
  transform: scale(0.95, 1);
}
</style>
