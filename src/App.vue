<template>
  <MapComponent />
  <div class="card-container">
    <p class="git-text">Press G for GitHubs</p>
    <GitHubCardComponent username="TuberculeP" />
    <GitHubCardComponent username="DalSchim" />
  </div>
  <DroidComponent />
  <ObstacleComponent />
  <VictoryComponent />
</template>

<script>

import gsap from 'gsap';
import DroidComponent from '@/components/DroidComponent.vue';
import GitHubCardComponent from '@/components/GitHubCardComponent.vue';
import MapComponent from '@/components/MapComponent.vue';
import ObstacleComponent from '@/components/ObstacleComponent.vue';
import VictoryComponent from '@/components/VictoryComponent.vue';

export default {
  name: 'App',
  components: {
    VictoryComponent,
    ObstacleComponent,
    GitHubCardComponent,
    DroidComponent,
    MapComponent,
  },
  mounted() {
    // while true pass, check if there is a collision, if yes, emmit an event and break
    const droid = document.querySelector('.droid');
    const obstacle = document.querySelector('.obstacle');

    function defeat() {
      console.log('defeat');
      document.querySelectorAll('.droid *, .background-scroll, .obstacle').forEach((el) => {
        gsap.killTweensOf(el);
      });
      document.querySelector('.victory').style.opacity = '1';
      document.querySelector('.obstacle').classList.add('collision');
    }

    const intervalId = setInterval(() => {
      if (this.isThereCollision(droid, obstacle)) {
        defeat();
        clearInterval(intervalId);
      }
    }, 100);

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
  methods: {
    isThereCollision(target, obstacle) {
      // récupérer l'offset par rapport à la fenêtre et la taille
      const targetRect = target.getBoundingClientRect();
      const obstacleRect = obstacle.getBoundingClientRect();
      // vérifier si les deux rectangles se chevauchent
      return !(
        targetRect.right < obstacleRect.left
        || targetRect.left > obstacleRect.right
        || targetRect.bottom < obstacleRect.top
        || targetRect.top > obstacleRect.bottom
      );
    },
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
