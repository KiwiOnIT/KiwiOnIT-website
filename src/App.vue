<template>
<About />

<div style="padding: 0rem 10%;">
  <Skill />
</div>

<Project />

<Footer />

</template>

<script>
import Skill from '@/components/Skill';
import About from '@/components/About';
import Project from '@/components/Project';
import Footer from '@/components/Footer';
export default {
	components: {Skill, About, Project, Footer},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
}
body {
  background-color: #2b2b2b;
  color: #ffffff;
}

.row {
  --bs-gutter-x: 0rem !important;
}
.min-vh-100 {
    min-height: 90vh!important;
}

.space {
  margin-left: 1% ;
}
</style>
