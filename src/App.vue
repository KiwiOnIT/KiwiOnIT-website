<template>
  <Background />
  <header id="header">
    <a href="https://github.com/KiwiOnIT" class="home">
      <img src="@/assets/Watermark.png" height="40" class="homeIMG" alt="Watermark">
    </a>
    <nav :class="{ 'open': isNavOpen }">
      <RouterLink to="/" @click="closeNav">Home</RouterLink>
      <RouterLink to="/about" @click="closeNav">About</RouterLink>
      <RouterLink to="/projects" @click="closeNav">Projects</RouterLink>
    </nav>
    <button @click="isNavOpen = !isNavOpen" class="hamburger" aria-label="Toggle navigation">
      <span class="bar"></span>
      <span class="bar"></span>
      <span class="bar"></span>
    </button>
  </header> 
  <RouterView />
  <div class="bar-footer">
    <br>
    <p class="footer">© 2024 | Made with ❤️ by Kiwi</p>
    <br>
  </div>
</template>

<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Background from './components/Background.vue'
import { ref } from 'vue';

const isNavOpen = ref(false);

const closeNav = () => {
  isNavOpen.value = false;
};
</script>

<script>
window.onscroll = function() {
    const header = document.getElementById('header');
    if (document.body.scrollTop > 50 || document.documentElement.scrollTop > 50) {
        header.classList.add('scrolled');
    } else {
        header.classList.remove('scrolled');
    }
};
</script>

<style scoped>
#app {
  font-family: Marianne, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
}

header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1000;
  display: flex;
  justify-content: space-between;
  align-items: center;
  backdrop-filter: blur(1rem);
  background-color: rgba(26, 27, 38, 0.6);
  transition: background-color 0.3s ease;
}

header.scrolled {
  background-color: rgba(26, 27, 38, 0.8);
}

nav {
  display: flex;
  align-items: center;
  text-align: center;
  padding: 15px 30px;
  background-color: rgba(0, 0, 0, 0); 
  font-size: 20px;
  justify-content: space-around;
  transition: max-height 0.3s ease;
}

nav.open {
  display: block;
  background-color: rgba(26, 27, 38, 0.8);
  backdrop-filter: blur(1rem);
}

nav a {
  color: #ffffff; /* Texte de base en blanc */
  text-decoration: none;
  padding: 5px 15px;
  display: flex;
  align-items: center;
  font-weight: bold;
  position: relative;
  overflow: hidden;
}

nav a::after {
  content: '';
  position: absolute;
  width: 0;
  height: 3px;
  background-color: #D499B9; /* Couleur de la barre */
  bottom: 0;
  left: 50%;
  transition: width 0.3s ease, left 0.3s ease;
}

nav a:hover::after {
  width: 100%;
  left: 0;
}

nav a:hover {
  color: #D499B9; /* Couleur du texte au survol */
}

.home {
  margin-left: 10px;
}

RouterView {
  margin-top: 60px; 
}

.hamburger {
  display: none;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background: transparent;
  border: none;
  cursor: pointer;
  margin-right: 20px;
}

.hamburger .bar {
  width: 25px;
  height: 3px;
  background-color: #D499B9;
  margin: 3px 0;
  transition: all 0.3s ease;
}

.bar-footer {
  height: 1px;
  width: 50vw;
  background-color: #D499B9;
  border-radius: 10px;
  margin-left: auto;
  margin-right: auto;
  margin-top: 3vh;
  text-align: center;
}

.footer {
  margin-top: 1.5rem;
  margin-bottom: 1.5rem;
  padding-top: 1rem;
  padding-bottom: 1rem;
  color: #fff;
}

@media (max-width: 768px) {
  nav {
    display: none;
    flex-direction: column;
    position: absolute;
    top: 60px;
    left: 0;
    right: 0;
    background: rgba(26, 27, 38, 0.9);
    padding: 15px;
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.3s ease;
  }

  nav.open {
    display: flex;
    max-height: 200px;
    background-color: rgba(26, 27, 38, 0.99);
    backdrop-filter: blur(1rem);
  }

  .home {
    margin-top: 10px;
  }

  .hamburger {
    display: flex;
  }
}
</style>
