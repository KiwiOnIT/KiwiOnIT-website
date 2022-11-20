<template>
<div class="card__grid">
  <div v-for="skill in images" :key="skill.id">
    <h1 class="text-white title-size" style="margin-top : 3.75rem;">{{skill.idName}}</h1>
    <div class="card__content">
      <div v-for="item in skill[skill.id]" :key="item.id">
        <div class="card__banner" :style="{ backgroundImage: `url('${item.image}')` }"></div>
        <h3 class="card__name">
          <strong>{{item.name}}</strong>
        </h3>
        <div class="card__jauge">
          <span v-if="['Compétences'].includes(skill.id)" class="percentage">{{ item.level }}%</span>
          <div class="card__jauge-bar">
              <div v-if="['Compétences'].includes(skill.id)" class="card__jauge-background"></div>
              <div v-if="['Compétences'].includes(skill.id)" class="bar" :style="{ backgroundColor: item.color, width: `${item.level}%` }" alt="Skill Image"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'SkillView',
  data() {
    return {
      images: []
    };
  },
  mounted() {
    this.images = [
      {
        id: "Compétences",
        idName: "Mes compétences",
        Compétences: [
          {
            name: "HTML",
            level: 80,
            color: "#e14d25",
            image: require("../assets/img/html5.png")
          },
          {
            name: "CSS",
            level: 50,
            color: "#006eba",
            image: require("../assets/img/css3.png")
          },
          {
            name: "C++",
            level: 10,
            color: "#06407f",
            image: require("../assets/img/cplusplus.png")
          },
          {
            name: "VueJs",
            level: 55,
            color: "#42b883",
            image: require("../assets/img/vuejs.png")
          },
          {
            name: "Javascript",
            level: 70,
            color: "#f0db4f",
            image: require("../assets/img/javascript.png")
          },
          {
            name: "Python",
            level: 35,
            color: "#009cff",
            image: require("../assets/img/python.png")
          }
        ]
      },
      {
        id: "Outils",
        idName: "Mes outils",
        Outils: [
          {
            name: "Windows",
            image: require("../assets/img/windows.png")
          },
          {
            name: "Ubuntu",
            image: require("../assets/img/ubuntu.png")
          },
          {
            name: "NodeJs",
            image: require("../assets/img/nodejs.png")
          },
          {
            name: "Npm",
            image: require("../assets/img/npm.png")
          },
          {
            name: "Git",
            image: require ("../assets/img/git.png")
          },
          {
            name: "Visual studio code",
            image: require ("../assets/img/vscode.png")
          }
        ]
      },
    ]
  }
}
</script>

<style scoped>

.card__content {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-gap: 50px 32px;
  gap: 50px 32px;
  margin: 1.5rem 0 2rem;
}

.card__name {
  margin-bottom: 0rem;
  padding: .5rem .75rem 0;
  background-color: rgb(50, 50, 50);
  display: flex;
  align-items: center;
  justify-content: flex-start;
}

.card__banner {
  background-repeat: no-repeat;
  background-position: 50%;
  background-size: 100% 180px;
  border-radius: 6px 6px 0 0;
  height: 170px;
  width: 100%;
  transition: .2s;
}

.card__banner:hover {
  background-size: 110% 200px; 
}

.skill-name {
  padding: .5rem .75rem 0;
}

.card__jauge {
  display: flex;
  margin-top: 0;
  align-items: center;
  background-color: rgb(50, 50, 50);
  justify-content: flex-start;
  padding: .5rem .75rem;
  width: 100%;
  border-radius:0px 0px 8px 8px;
}
.percentage {
  white-space: nowrap;
}

.card__jauge-bar {
  position: relative;
  margin: 0 20px;
  width: 100%;
}

.card__jauge-background {
  position: absolute;
  background-color: #fff;
  border-radius: 6px;
  height: 5px;
  width: 100%;
}

.bar {
  position: absolute;
  border-radius: 6px;
  height: 5px;
}

.title-size {
  font-size: 54px;
}

@media only screen and (max-width: 1500px) {
  .card__content {
    grid-template-columns: 1fr 1fr;
  }
}
@media only screen and (max-width: 1000px) {
  .card__content {
    grid-template-columns: 1fr;
  }
}
@media only screen and (max-width: 600px) {
  .card__banner {
    background-size: 100% 150px;
    height: 140px;
  }
}
</style>
