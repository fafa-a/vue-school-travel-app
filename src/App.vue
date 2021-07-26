<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <br />
  <router-link :to="{ path: '/' }">Home</router-link> |
  <router-link :to="{ path: '/about' }">About</router-link>
  <RouterView />
</template>

<script setup>
// This starter template is using Vue 3 experimental <script setup> SFCs
// Check out https://github.com/vuejs/rfcs/blob/master/active-rfcs/0040-script-setup.md
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
