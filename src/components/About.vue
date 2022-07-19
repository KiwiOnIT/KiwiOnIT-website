<template>
<div class="row">
  <div>
    <a href="https://github.com/KiwiOnIT" class="home">
      <img src="@/assets/Watermark.png" height="40" class="homeIMG">
    </a>
  </div>
</div>

<div class="row justify-content-md-center vertical-center d-flex align-items-center space min-vh-100">
  <div class="col col-4 col-lg-4 test">
    <h1 class="title">Salut !<img src="https://github.com/SatYu26/SatYu26/raw/master/Assets/Hi.gif" width="30px"></h1>
    <p class="title">Je m'appelle <strong class="title-name">Anthonin (Kiwi)</strong></p>
  </div>
  <div class="col-md-auto space">
    <img src="@/assets/logo.png"  class="logo" width="400" height="400">
  </div>
</div>
</template>

<script>
export default {
    name:'AboutView',
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
  color:aqua;
  font-weight: bold;
}
.logoDiv {
  float: right;
  margin-right: 475px;
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

@media screen and (max-width: 600px)
{
  .logo {
    width: 300px;
    height: 300px;
  }
  .title {
    font-size: 25px;
  }
  .text {
    font-size: 15px;
  }
  .test {
    width: 50%!important;
    margin-top: 10vh!important;
    margin-bottom: 5vh!important;
    margin-right: auto!important;
    margin-left: auto!important;
  }
  .min-vh-100 {
    min-height: 0vh!important;
  }
}
</style>