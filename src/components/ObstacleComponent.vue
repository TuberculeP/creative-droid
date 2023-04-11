<template>
<div class="obstacle-container">
  <div class="obstacle"></div>
</div>
</template>

<script>
// eslint-disable-next-line import/no-extraneous-dependencies
import { gsap } from 'gsap';

export default {
  name: 'ObstacleComponent',
  mounted() {
    gsap.set('.obstacle', { x: 0 });
    gsap.to('.obstacle', {
      x: -window.innerWidth,
      duration: 5,
      ease: 'linear',
      repeat: -1,
    });
  },
};
</script>

<style scoped>
.obstacle-container{
  position: absolute;
  bottom: 75px;
  left: 0;
  width: 100%;
}
.obstacle{
  width: 100px;
  height: 100px;
  background-color: #2c3e50;
  position: absolute;
  right: 0;
  bottom: 0;
}
</style>
