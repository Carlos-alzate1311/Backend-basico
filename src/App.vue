
import { RouterLink } from 'vue-router';


import { RouterLink } from 'vue-router';


import { RouterLink } from 'vue-router';

<template>
  <div id="app">

    <div class="imgensayo"><img src="./assets/FD.jpg"/></div>
    <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> |
      <router-Link to="/cliente">Cliente</router-Link> |
      <RouterLink to="/barbero">Barberos</RouterLink>
    </nav>
    <router-view/>

    <footer> pie de ppagina</footer>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #391f09;
  background-color: bisque;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #1015ab;
}

nav a.router-link-exact-active {
  color: #c81010b2;
}


</style>
