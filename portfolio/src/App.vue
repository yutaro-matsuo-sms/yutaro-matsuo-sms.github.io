<template>
  <div id="app">
    <header>
      <h1 class="logo">
        <img src="./assets/pic/head_logo.jpg" alt="hello,world" width="250" height="80" />
      </h1>
      <nav>
        <ul>
          <li class="Profile">
            <p>Profile</p>
          </li>
          <li class="Works">
            <p>Works</p>
          </li>
          <li class="Contents">
            <p>Contents</p>
          </li>
          <li class="comingsoon">
            <p>Coming soon...</p>
          </li>
        </ul>
      </nav>
      <ul class="snsBtn">
        <li>
          <a href="https://www.instagram.com/piggyof9071/?hl=ja">
            <img src="./assets/pic/insta_icon.png" alt="Instagram" width="70" height="70" />
          </a>
        </li>
      </ul>
    </header>
    <div class="profile">
      <h2>Profile</h2>
      <img class="profImage" src="./assets/pic/IMG_1310_Original.jpeg" alt />
      <dl class="prof">
        <dt>氏名:</dt>
        <dd>松尾友太郎</dd>
        <dt>生年月日</dt>
        <dd>1997年9月17日</dd>
        <dt>所在地:</dt>
        <dd>東京都</dd>
        <dt>出生地</dt>
        <dd>福島県</dd>
        <dt>業務:</dt>
        <dd>Webエンジニア(自称)</dd>
        <dt>スポーツ</dt>
        <dd>バスケットボール</dd>
      </dl>
    </div>
    <div class="contents">
      <h2>Contents</h2>
      <PhotoContainer v-bind:photos="photos" />
    </div>
  </div>
</template>

<script>
import PhotoContainer from "./components/PhotoContainer";

export default {
  name: "App",
  components: {
    PhotoContainer
  },
  data: function() {
    return {
      photos: [
        require("./assets/pic/slider/0AA396A2-B13D-4DCC-8696-D28583EEBD0D_Original.jpg"),
        require("./assets/pic/slider/904DC860-D98E-4043-B7A4-514823076288_Original.jpg"),
        require("./assets/pic/slider/A4BA17EB-0532-45D9-B7F2-42BE2C3872A4_Original.jpg"),
        require("./assets/pic/slider/DCFCF608-B5A4-4A6A-9CF8-1DF22021DFB2_Original.jpg"),
        require("./assets/pic/slider/E54EE37D-55EB-45B7-BFC4-BFB3664E17E2_Original.jpg"),
        require("./assets/pic/slider/IMG_2689.jpeg")
      ]
    };
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#app {
  font-size: 14px;
  color: #333;
  line-height: 1.9;
  text-align: center;
  margin: 0;
  font-weight: normal;
}

header {
  margin-bottom: 25px;
  display: block;
}

h1.logo {
  text-align: left;
  margin: 0 auto;
  padding-left: 30px;
  text-align: left;
}

nav {
  border-top: 1px solid #d9d9d9;
}

nav ul {
  display: flex;
  list-style-type: none;
}

nav li {
  float: left;
  width: 50%;
  border-bottom: 1px solid #d9d9d9;
  text-align: center;
}

li {
  display: list-item;
}

ul.snsBtn {
  max-width: 50%;
  text-align: center;
  margin: 0 auto;
}

ul.snsBtn li {
  display: inline;
}

ul {
  padding: 0;
}

.prof {
  margin-bottom: 25px;
  font-size: 11px;
}

.profImage {
  width: 20%;
}

.prof dt {
  padding-left: 20%;
  float: left;
  display: block;
  width: 30%;
  font-weight: bold;
}

.prof dd {
  margin-left: 80px;
  width: 70%;
  font-size: 12px;
}

.slide_show {
  width: 100%;
  max-width: 640px;
  overflow: hidden;
  position: relative;
  margin: 0 auto;
}

.slide_pic {
  width: 10000px;
  list-style: none;
}

.slide_pic li {
  float: left;
}

#nav_btn .prev {
  position: absolute;
  left: 10px;
  top: 35%;
  margin-top: -25px;
}

#nav_btn .next {
  position: absolute;
  right: 10px;
  top: 35%;
  margin-top: -25px;
}
</style>
