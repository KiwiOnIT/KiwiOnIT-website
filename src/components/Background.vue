<template>
  <div class="background">
    <div class="star" v-for="i in starCount" :key="i" :style="getStarStyle()"></div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const starCount = ref(500);

const getStarStyle = () => {
  const size = Math.random() * 3 + 1 + 'px';
  const left = Math.random() * 100 + 'vw';
  const top = Math.random() * 100 + 'vh';
  return {
    position: 'absolute',
    borderRadius: '50%',
    backgroundColor: 'rgba(255, 255, 255, 0.8)',
    animation: 'twinkle 3s infinite', // Adjusted animation duration
    opacity: Math.random(),
    width: size,
    height: size,
    left: left,
    top: top
  };
};

onMounted(() => {
  const stars = document.querySelectorAll('.star');
  stars.forEach(star => {
    const delay = Math.random() * 5;
    star.style.animationDelay = `${delay}s`;
  });
});
</script>

<style scoped>
.background {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  overflow: hidden;
  z-index: -1; 
  background-color: rgba(0, 0, 0, 0.5);
}

.star {
  width: 5px;
  height: 5px;
}

@keyframes twinkle {
  0% {
    opacity: 0;
  }
  50% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}
</style>