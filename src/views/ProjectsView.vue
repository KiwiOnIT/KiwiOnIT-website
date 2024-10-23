<template>
    <div class="projects-section">
      <h1 class="title title-margin">My projects</h1>
      <div class="__container">
        <div v-for="item in images" :key="item.name" class="card">
          <div class="card-img" :style="{ backgroundImage: `url(${item.image})` }" alt="Project Image">
            <div class="overlay">
              <div class="overlay-content">
                <a :href="item.link" target="_blank">View github</a>
              </div>
            </div>
          </div>
          <div class="card-body card-content">
            <h2>{{ item.name }}</h2>
            <p>{{ item.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import passlyImage from '../assets/img/passly.webp';
  import paraImage from '../assets/img/para.png';
  import logowbgImage from '../assets/img/logowbg.png';
  import pfcImage from '../assets/img/pfc.png';
  import penduImage from '../assets/img/pendu.png';
  import guessImage from '../assets/img/Guess-a-number.png';
  
  export default {
    name: 'ProjectView',
    data() {
      return {
        images: [
          {
            name: "Passly",
            description: "Password generator in VueJs",
            link: "https://github.com/KiwiOnIT/Passly",
            image: passlyImage,
          },
          {
            name: "Para bot",
            description: "Discord bot in Djs14 (outdated)",
            link: "https://github.com/KiwiOnIT/Para-Bot",
            image: paraImage,
          },
          {
            name: "Flop website",
            description: "Website for an autoclicker",
            link: "https://github.com/KiwiOnIT/flop-website",
            image: logowbgImage,
          },
          {
            name: "Rock, Paper, Scissors",
            description: "Mini game in Python",
            link: "https://github.com/KiwiOnIT/Pierre-feuille-ciseaux",
            image: pfcImage,
          },
          {
            name: "Hangman game",
            description: "Mini game in C++",
            link: "https://github.com/KiwiOnIT/JeuDuPendu",
            image: penduImage,
          },
          {
            name: "Guess the number",
            description: "Mini game in C++",
            link: "https://github.com/KiwiOnIT/PlusOuMoins",
            image: guessImage,
          },
        ],
      };
    },
  };
  </script>
  
  <style scoped>
  .projects-section {
    padding: 1rem;
    margin-top: 3vh;
  }
  
  .title-margin {
    margin-top: 3rem;
    text-align: center;
  }
  
  .__container {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    gap: 1.5rem;
    margin-top: 5.5rem;
  }
  
  .card {
    width: 300px;
    background-color: #24283b;
    margin: 1rem;
    border-radius: 4px;
    overflow: hidden;
    box-shadow: #D499B9 0px 2px 4px 0px, #D499B9 0px 2px 16px 0px;
    transition: transform 0.2s ease;
    border: 1px solid #D499B9
  }
  
  .card:hover {
    transform: translateY(-4px);
    border: 2px solid #dd80b3;
  }
  
  .card-img {
    height: 200px;
    background-position: center;
    background-size: cover;
    position: relative;
  }
  
  .overlay {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: rgba(0, 0, 0, 0.5);
    opacity: 0;
    transition: opacity 0.3s ease;
  }
  
  .card:hover .overlay {
    opacity: 1;
  }
  
  .overlay-content {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
  }
  
  .overlay-content a {
    color: white;
    text-decoration: none;
    border: 1px solid white;
    padding: 0.5rem 1rem;
    border-radius: 20px;
    transition: background-color 0.3s ease;
  }
  
  .overlay-content a:hover {
    background-color: #c0caf5;
  }
  
  .card-body {
    padding: 1rem;
    text-align: center;
  }
  
  .card-content h2 {
    font-size: 1.25rem;
    font-weight: 500;
    color: white;
  }
  
  .card-content p {
    font-size: 0.875rem;
    color: #ffffffc4;
  }

  .title {
    color: white;
    font-size: 40px;
    font-weight: bold;
  }
</style>
