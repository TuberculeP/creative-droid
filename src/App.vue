<template>
  <div class="card-container">
    <p class="git-text">Press G for GitHubs</p>
    <GitHubCardComponent username="TuberculeP" />
    <GitHubCardComponent username="DalSchim" />
  </div>
  <DroidComponent />
</template>

<script>

import gsap from 'gsap';
import DroidComponent from '@/components/DroidComponent.vue';
import GitHubCardComponent from '@/components/GitHubCardComponent.vue';

export default {
  name: 'App',
  components: {
    GitHubCardComponent,
    DroidComponent,
  },
  mounted() {
    window.addEventListener('keypress', (e) => {
      if (e.key === 'g') {
        gsap.to('.git-text', {
          opacity: 0,
          duration: 1,
          ease: 'power4.out',
        });
      }
    });
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body{
  margin: 0;
  padding: 0;
}

#logo{
  width: 200px;
}

.card-container{
  position: absolute;
  bottom: 20px;
  right: 20px;
  display: flex;
  align-items: center;
  gap: 20px;
}
</style>
