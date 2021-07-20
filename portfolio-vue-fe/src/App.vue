<template>
  <div id="app">
    
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <index/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import index from './pages/index.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld
    index,
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;700;800;900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');
* {
  margin:0;
  border:0;
}

#app {
  font-family: 'Roboto','Orbitron', sans-serif;
  font-weight:light;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #F3F3F3;
}
</style>
