<template>
  <div class="container">
    <h1 class="title">A little about <span class="color">ME</span></h1>
    <div class="column">
      <p class="text">Hi guys, I'm <strong class="color">Anthonin</strong> a.k.a <strong class="color">KiwiOnIT</strong>, a 17-year-old aspiring developer passionate about cybersecurity.
       I'm dedicated to learning the foundations of programming and constantly improving my skills.</p>
       <h1>My other <strong class="color">Interests</strong> :</h1>
       <p class="text"> - Reading manga<br>
                        - Playing Video games
       </p>
       <h1>My school <strong class="color">career</strong> :</h1>
    </div>
    <div class="timeline">
         <div class="timeline-item">
           <div class="timeline-circle"></div>
           <div class="timeline-line"></div>
           <div class="timeline-content">
             <strong>Lycée Thomas Corneille, Barentin (2022-2025)</strong>
           </div>
         </div>
         <div class="timeline-item">
           <div class="timeline-circle"></div>  
           <div class="timeline-content">
             <strong>Soon (i hope im accepted in prépa)</strong>
           </div>
         </div>
       </div>
  </div>
  <div class="card__grid">
    <div v-for="skill in images" :key="skill.id">
      <h1 class="title-size" style="margin-top: 3.75rem;">{{ skill.idName }}</h1>
      <div class="card__content">
        <div v-for="item in skill[skill.id]" :key="item.name" class="box">
          <img :src="item.image" alt="Skill Image" class="card__image" />
          <h3 class="card__name">
            <strong>{{ item.name }}</strong>
          </h3>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import htmlImage from '../assets/img/html5.png';
import cssImage from '../assets/img/css3.png';
import cppImage from '../assets/img/cplusplus.png';
import vueImage from '../assets/img/vuejs.png';
import jsImage from '../assets/img/javascript.png';
import pythonImage from '../assets/img/python.png';
import windowsImage from '../assets/img/windows.png';
import ubuntuImage from '../assets/img/ubuntu.png';
import nodeImage from '../assets/img/nodejs.png';
import npmImage from '../assets/img/npm.png';
import gitImage from '../assets/img/git.png';
import vscodeImage from '../assets/img/vscode.png';

export default {
  data() {
    return {
      images: []
    };
  },
  mounted() {
    this.images = [
      {
        id: "Compétences",
        idName: "My skills",
        Compétences: [
          {
            name: "HTML",
            image: htmlImage
          },
          {
            name: "CSS",
            image: cssImage
          },
          {
            name: "C++",
            image: cppImage
          },
          {
            name: "VueJs",
            image: vueImage
          },
          {
            name: "Javascript",
            image: jsImage
          },
          {
            name: "Python",
            image: pythonImage
          }
        ]
      },
      {
        id: "Outils",
        idName: "My tools",
        Outils: [
          {
            name: "Windows",
            image: windowsImage
          },
          {
            name: "Ubuntu",
            image: ubuntuImage
          },
          {
            name: "NodeJs",
            image: nodeImage
          },
          {
            name: "Npm",
            image: npmImage
          },
          {
            name: "Git",
            image: gitImage
          },
          {
            name: "Visual Studio Code",
            image: vscodeImage
          }
        ]
      }
    ];
  }
};
</script>

<style scoped>
.container {
  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 10vh;
  color: #fff;
  flex-direction: column;
}

.title {
  font-size: 54px;
}
.text {
  font-size: 20px;
}
.column {
  width: 50vw;
}
.color {
  color: #D499B9;
}
.card__grid {
  text-align: center;
}

.card__content {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  gap: 30px;
  margin: 1.5rem 0 2rem;
}

.box {
  background-color: #24283b;
  border-radius: 8px;
  padding: 1rem;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  transition: transform 0.2s;
  max-width: 200px;
  width: 100%;
  box-shadow: #D499B9 0px 1px 3px, #D499B9 0px 1px 2px;
  border: 1px solid #D499B9
}

.box:hover {
  transform: scale(1.05);
  border: 2px solid #dd80b3;
}

.card__image {
  width: 100px;
  height: 100px;
  object-fit: contain;
  margin-bottom: 0.5rem;
}

.card__name {
  margin: 0;
  color: white;
  font-size: 18px;
  font-weight: bold;
}

.title-size {
  font-size: 54px;
  color: white;
  text-align: center;
}

.timeline {
  position: relative;
  margin: 20px 0;
  margin-left: -300px;
}

.timeline-item {
  position: relative;
  padding: 10px 0;
}

.timeline-circle {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  width: 20px;
  height: 20px;
  background-color: #D499B9;
  border-radius: 50%;
  z-index: 1;
}

.timeline-line {
  position: absolute;
  left: 50%;
  top: 20px;
  transform: translateX(-50%);
  width: 2px;
  height: 50px;
  background-color: #D499B9;
  z-index: 0;
}

.timeline-content {
  position: relative;
  padding-left: 30px;
  margin-left: 320px;
  text-align: left;
}

@media only screen and (max-width: 1500px) {
  .card__content {
    gap: 30px;
  }
}
@media only screen and (max-width: 800px) {
  .card__image {
    width: 80px;
    height: 80px;
  }
  .title-size {
    font-size: 48px;
  }
  .column {
    width: 100%;
  }

  .timeline-content{
    font-size: 12px;
  }
}
</style>