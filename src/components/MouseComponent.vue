<template>
  <div class="mouse"></div>
</template>

<script>
// eslint-disable-next-line import/no-extraneous-dependencies
import { gsap } from 'gsap';

export default {
  name: 'MouseComponent',
  mounted() {
    const mouse = document.querySelector('.mouse');
    const right = window.innerWidth - mouse.offsetWidth;
    const top = mouse.offsetHeight - window.innerHeight;
    const tl = gsap.timeline({ repeat: -1 });

    [
      { x: right, y: 0 },
      { x: right, y: top },
      { x: 0, y: top },
      { x: 0, y: 0 },
    ].forEach((point, index) => {
      tl.to('.mouse', {
        duration: 3,
        x: point.x,
        y: point.y,
        ease: 'inOut',
      });
      // rotations : 1: -90, 2: -180, 3: -270, 4: -360
      tl.to('.mouse', { rotate: -90 * (index + 1) });
    });
  },
};
</script>

<style scoped>
div.mouse{
  width: 50px;
  height: 50px;
  background-image: url('https://www.templeofbricks.com/img/minifigs/lego-star-wars/minifig-lego-star-wars-sw1004.png');
  background-size: cover;
  background-position: center;
  position: fixed;
  bottom: 0;
  left: 0;
}
</style>
