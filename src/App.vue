<template>
  <div class="card-container">
    <GitHubCardComponent username="TuberculeP" />
    <GitHubCardComponent username="DalSchim" />
  </div>
  <DroidComponent />
</template>

<script>

import DroidComponent from '@/components/DroidComponent.vue';
import GitHubCardComponent from '@/components/GitHubCardComponent.vue';

export default {
  name: 'App',
  components: {
    GitHubCardComponent,
    DroidComponent,
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
  top: 20px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  align-items: center;
  gap: 20px;
}
</style>
