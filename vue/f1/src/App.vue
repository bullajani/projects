<template>
  <div>
    <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld />
  
 
  <router-link to="/">
      <button>Signup</button>
    </router-link>
    <br>

    <!-- Correct the router-link for Home -->
    <router-link to="/home">
      <button>Home</button>
    </router-link>

    <router-view></router-view>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue' 
import homepage from './components/home.vue'


export default {
  name: 'App',
  components: {
     HelloWorld ,
     homepage ,
  
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
