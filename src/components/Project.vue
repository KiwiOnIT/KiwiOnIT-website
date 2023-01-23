<template>
<h1 class="text-white title-size" style="margin-top : 10.75rem;">Mes projets</h1>
<div class="__container" style="margin-top : 5.5rem;">
  <div v-for="item in images" :key="item.id" class="card" style="width: 18rem;">
    <div class="card-img card-img-top" :style="{ backgroundImage: `url('${item.image}')` }" alt="Project Image">
      <div class="overlay">
        <div class="overlay-content">
           <a :href="item.link">View github</a>
        </div>
      </div>
    </div>
    <div class="card-body card-content">
      <h2>{{item.name}}</h2>
      <p>{{item.description}}</p>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name:'ProjectView',
  data() {
    return {
      images: []
    };
  },
  mounted() {
    this.images = [
      {
        name: "Passly",
        description: "Generateur de password en VueJs",
        link: "https://github.com/KiwiOnIT/Passly",
        image: require("../assets/img/passly.webp")
      },
      {
        name: "Para bot",
        description: "Bot Discord Js v14",
        link: "https://github.com/KiwiOnIT/Para-Bot",
        image: require("../assets/img/para.png"),
      },
      {
        name: "Flop website",
        description: "Site web en VueJs pour Flop Clicker",
        link: "https://github.com/KiwiOnIT/flop-website",
        image: require("../assets/img/logowbg.png")
      },
      {
        name: "Pierre, Feuille, Ciseaux",
        description:"Mini jeu codé en Python",
        link:"https://github.com/KiwiOnIT/Pierre-feuille-ciseaux",
        image: require("../assets/img/pfc.png")
      },
      {
        name: "Jeu du pendu",
        description: "Mini jeu codé en C++",
        link: "https://github.com/KiwiOnIT/JeuDuPendu",
        image: require("../assets/img/pendu.png")
      },
      {
        name: "Guess the number",
        description: "Mini jeu codé en C++",
        link: "https://github.com/KiwiOnIT/PlusOuMoins",
        image: require ("../assets/img/Guess-a-number.png")
      },
    ]
  }
}
</script>

<style scoped>

.box {
  width: 100px;
  height: 100px;
  background-color: rgb(50, 50, 50);
  border-radius: 12px;
  margin-top: 50px;
  box-shadow: rgba(0, 0, 0, 0.25) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
}
.title-size {
  font-size: 54px;
}
.card {
  width: 300px;
  display: inline-block;
  background-color: #2b2b2b!important;
  margin: 1rem;
  border-radius: 4px;
  box-shadow: rgba(0, 0, 0, 0.25) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
  transition: all 0.2s ease;
  background: #fff;
  position: relative;
  overflow: hidden;
}
.card:hover, .card.hover {
  transform: translateY(-4px);
  box-shadow: rgba(0, 0, 0, 0.25) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
}
.card:hover .card-content, .card.hover .card-content {
  box-shadow: inset 0 3px 0 0 #5ea4cc;
  border-color: #5ea4cc;
}
.card:hover .card-img .overlay, .card.hover .card-img .overlay {
  background-color: rgba(25, 29, 38, .85);
  transition: opacity 0.2s ease;
  opacity: 1;
}
.card-img {
  position: relative;
  height: 224px;
  width: 100%;
  background-color: #fff;
  transition: opacity 0.2s ease;
  background-position: center center;
  background-repeat: no-repeat;
  background-size: cover;
}
.card-img .overlay {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: #fff;
  opacity: 0;
}
.card-img .overlay .overlay-content {
  line-height: 224px;
  width: 100%;
  text-align: center;
  color: #fff;
}
.card-img .overlay .overlay-content a {
  color: #fff;
  padding: 0 2rem;
  display: inline-block;
  border: 1px solid rgba(255, 255, 255, .4);
  height: 40px;
  line-height: 40px;
  border-radius: 20px;
  cursor: pointer;
  text-decoration: none;
}
.card-img .overlay .overlay-content a:hover, .card-img .overlay .overlay-content a.hover {
  background: #5ea4cc;
  border-color: #5ea4cc;
}
.card-content {
  min-height: 104px;
  background-color: rgb(50, 50, 50)!important;
  border-top: 1px solid #181717!important;
  border-bottom-right-radius: 4px;
  border-bottom-left-radius: 4px;
  padding: 1rem 2rem;
  transition: all 0.2s ease;
}
.card-content a {
  text-decoration: none;
  color: #202927;
}
.card-content h2, .card-content a h2 {
  font-size: 1rem;
  font-weight: 500;
}
.card-content p, .card-content a p {
  font-size: 0.8rem;
  font-weight: 400;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  color: #ffffffc4;
}
@media screen and (max-width: 800px)
{
  .box {
    margin-left: 20px;
  }
  .__container {
    display: block;
    margin-left: auto;
    margin-right: auto;
  }
}
</style>
