<template>
<div class="victory">
  <h1>Ce fut star wars.</h1>
</div>
</template>

<script>
export default {
  name: 'VictoryComponent',
};
</script>

<style scoped>
.victory{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
  opacity: 0;
}
</style>
