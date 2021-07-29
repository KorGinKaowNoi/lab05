<template>
<div id="flashMessage" v-if="Gstore.flashMessage">
  {{Gstore.flashMessage}}
</div>
  <div id="nav">
    <router-link :to="{ name: 'EventList' }">Home</router-link> |
    <router-link :to="{ name: 'About' }">About</router-link>
  </div>

  <!-- new element -->
  <router-view />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
h4 {
  font-size: 20px;
}
@keyframes yellowfade {
  from{
    background:yellow;
  }
  to{
    background: transparent;
  }
}
#flashMessage{
  animation-name: yellowfade;
  animation-duration: 3s;
}
</style>
<script>
export default {
  inject:['Gstore']
}
</script>