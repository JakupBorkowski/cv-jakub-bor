<template>
  <Navbar></Navbar>
  <div class="banner">
    <router-view>

    </router-view>
  </div>

</template>

<script>

import Navbar from './components/Navbar.vue'

export default {
  name: 'App',
  components: {
    Navbar,
  }
}
</script>

<style>
*{
  margin: 0 auto;
  padding: 0;
  font-family: sans-serif;
}
.banner{
  width: 100%;
  min-height:100vh;
  background-image: linear-gradient(rgba(0,0,0,0.1),rgba(0,0,0,0.1)),url(./assets/tlo.png);
  background-size: cover;
  background-position: center;
}
</style>
