<template>
  <div class="container">
    <div class="content-1">
      <h1 class="title">Hey !<span class="wave-emoji">👋🏻</span></h1>
      <p class="text">I'm <strong class="title-name">Anthonin</strong> a.k.a <strong class="title-name">KiwiOnIT</strong></p>
      <typing class="title typing" />
    </div>
    <div class="content-2">
      <img src="@/assets/logo.png" class="logo" width="400" height="400" />
    </div>
  </div>
    <!-- Snake game, only shown on PC -->
    <div class="snake-container" v-if="isPC">
      <SnakeGame />
    </div>
</template>

<script>
import Typing from '../components/Typing.vue'
import SnakeGame from '../components/SnakeGame.vue'

export default {
  components: { Typing, SnakeGame },
  data() {
    return {
      isPC: window.innerWidth > 800 // Only show on PC-sized screens
    };
  },
  mounted() {
    window.addEventListener('resize', this.checkScreenSize);
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.checkScreenSize);
  },
  methods: {
    checkScreenSize() {
      this.isPC = window.innerWidth > 800;
    }
  }
}
</script>

<style scoped>

@keyframes wave {
  0% { transform: rotate(0deg); }
  10% { transform: rotate(14deg); }
  20% { transform: rotate(-8deg); }
  30% { transform: rotate(14deg); }
  40% { transform: rotate(-4deg); }
  50% { transform: rotate(10deg); }
  60% { transform: rotate(0deg); }
  100% { transform: rotate(0deg); }
}

.space{
  margin-top:20vh;
}

.wave-emoji {
  display: inline-block;
  font-size: 1.5em;
  animation: wave 1.5s ease-in-out infinite;
  transform-origin: 70% 70%;
}

.title {
  font-size: 40px;
  color: #ffffff;
  text-align: left;
}

.text {
  text-align: left;
  color: rgb(201, 199, 199);
  font-size: 24px;
}

.title-name {
  color: #D499B9;
  font-weight: bold;
}

.logo {
  box-shadow: #D499B9 0px 1px 3px, #D499B9 0px 1px 2px;
  border-radius: 16px;
}

.container {
  margin-top: 25vh;
  display: flex;
  justify-content: center;
  align-items: flex-start;
  text-align: center;
}

.content-1 {
  margin-right: 5vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.content-2 {
  display: flex;
  justify-content: center;
  align-items: center;
}

.typing {
  margin-top: -10px; 
  text-align: left;
  width: fit-content;
}

.snake-container {
  margin-top:40vh;
}

@media screen and (max-width: 800px) {
  .logo {
    width: 300px;
    height: 300px;
  }
  .title {
    font-size: 28px;
  }
  .text {
    font-size: 18px;
  }
  .container {
    flex-direction: column;
    align-items: center;
    margin-top: 10vh;
  }
  .content-1 {
    margin-right: 0;
  }
  .snake-container {
    display: none;
  }
}
</style>