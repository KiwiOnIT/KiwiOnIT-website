<template>
<div class="row">
  <div>
    <a href="https://github.com/KiwiOnIT" class="home">
      <img src="@/assets/Watermark.png" height="40" class="homeIMG">
    </a>
  </div>
</div>

<div class="row justify-content-md-center vertical-center d-flex align-items-center min-vh-100 space">
  <div class="col col-lg-2">
    <h1 class="title">Salut ! Je m'appelle Anthonin (Kiwi) <img src="https://github.com/SatYu26/SatYu26/raw/master/Assets/Hi.gif" width="30px" style="display:initial;vertical-align:initial;"></h1>
    <p class="text">Je suis un jeune développeur qui touche à quelques langages et les utilise pour des petits projets</p>
  </div>
  <div class="col-md-auto space">
    <img src="@/assets/logo.png"  class="logo" width="400" height="400">
  </div>
</div>
</template>

<script>
export default {
    name:'AboutView'
}
</script>

<style scoped>
.title {
  font-weight: bold;
  font-size: 30px;
  color: #ffffff;
}
.text  {
  font-size: 20px;
  color: #ffffffc9;
}
.logoDiv {
  float: right;
  margin-right: 475px;
  margin-top: 250px;
}
.logo {
  border-radius: 8px;
  box-shadow: rgba(0, 0, 0, 0.25) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
}
.home {
  float: left;
  margin-left: 12px;
  margin-top: 8px;
}

@media screen and (max-width: 1280px)
{
  .center {
    margin-left: 25px;
  }
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
}
</style>