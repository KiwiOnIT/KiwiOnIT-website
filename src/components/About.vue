<template>
  <div class="header">
    <a href="https://github.com/KiwiOnIT" class="home">
      <img src="@/assets/Watermark.png" height="40" class="homeIMG" alt="Watermark">
    </a>
  </div>

<div class="container">
  <div class="content-1">
    <h1 class="title">Salut !<img src="https://github.com/SatYu26/SatYu26/raw/master/Assets/Hi.gif" width="30px" alt="Hey emojie"></h1>
    <p class="title">Je m'appelle <strong class="title-name">Anthonin (Kiwi)</strong></p>
    <typing class="title typing"/>
  </div>
  <div class="content-2">
    <img src="@/assets/logo.png"  class="logo" width="400" height="400">
  </div>
</div>
</template>

<script>
import Typing from '@/components/Typing'
export default {
    name:'AboutView',
    components: {Typing}
}
</script>

<style scoped>
.about {
  margin-right: 300px;
}

.title {
  font-size: 40px;
  color: #ffffff;
  text-align: left;
}

.title-name {
  color:#00ffff;
  font-weight: bold;
}
.logoDiv {
  margin-top: 250px;
}
.logo {
  box-shadow: rgba(0, 0, 0, 0.25) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
  border-radius: 16px
}
.home {
  float: left;
  margin-left: 12px;
  margin-top: 8px;
}

.container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.content-1 {
  flex: 0 0 33.3333%;
  max-width: 33.3333%;
  margin-right: 1%;
}

.content-2 {
  flex: 0 0 auto;
}

.header {
  width: 100%;
  height: 7vh;
}

.typing {
  text-align: left;
  width: fit-content;
}
@media screen and (max-width: 800px)
{
  .logo {
    width: 300px;
    height: 300px;
  }
  .title {
    font-size: 24px;
    text-align: center;
  }
  .text {
    font-size: 15px;
  }
  .container {
    flex-direction: column;
    margin-left: auto;
    margin-right: auto;
    display: block;
  }
  .content-1 {
    order: 1;
    max-width: 100%;
  }
  .content-2 {
    order: 2;
  }
}
</style>