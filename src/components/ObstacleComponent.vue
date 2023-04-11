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
      duration: 4,
      rotate: -360 * 5,
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
  position: absolute;
  width: 100px;
  height: 100px;
  background: url("@/assets/bomb.png") center;
  background-size: contain;
  border-radius: 50%;
  right: 0;
  bottom: 0;
}

.obstacle.collision{
  background: url("@/assets/explosion.gif");
  width: 200px;
  height: 200px;
}
</style>
