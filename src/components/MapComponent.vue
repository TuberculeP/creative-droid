<template>
  <div class="background-scroll"></div>
</template>
<script>
import gsap from 'gsap';

export default {
  name: 'MapComponent',
  mounted() {
    gsap.set('.background-scroll', { backgroundPosition: '0 bottom' });
    gsap.to('.background-scroll', {
      backgroundPosition: '-2000px bottom',
      duration: 8,
      ease: 'linear',
      repeat: -1,
    });
  },
};
</script>
<style lang="scss">
.background-scroll {
  position: relative;
  width: 100%;
  height: 100vh;
  background-image: url('@/assets/bg.jpg');
  background-repeat: repeat-x;
  background-size: cover;
  background-position: 0 0;
  animation: scroll-background 8s linear infinite;
}
</style>
