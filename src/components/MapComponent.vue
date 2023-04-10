<template>
    <div class="background-scroll"></div>
</template>
<script>
export default {
  name: 'MapComponent',
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
    animation: scroll-background 8s linear infinite;
}
@keyframes scroll-background {
    0% {
        background-position: 0 0;
    }
    100% {
        background-position: -2000px 0;
    }
}
</style>
