<template>
  <DroidComponent />
  <!--
  <MouseComponent />
  -->
</template>

<script>

// import MouseComponent from '@/components/MouseComponent.vue';
import DroidComponent from '@/components/DroidComponent.vue';

export default {
  name: 'App',
  components: {
    DroidComponent,
    // MouseComponent
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
</style>
