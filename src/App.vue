<template>
  <div id="app">
    <img src="./assets/logo.png">
    <Animations/>
  </div>
</template>

<script>
import Animations from './components/Animations';

export default {
  name: 'App',
  components: {
    Animations,
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

img {
  max-height: 60px;
}
</style>
