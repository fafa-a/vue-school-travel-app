<template>
  <div id="nav">
    <router-link :to="{ path: '/' }">Home</router-link>
    <router-link :to="{ path: '/brazil' }">Brazil</router-link>
    <router-link :to="{ path: '/hawaii' }">Hawaii</router-link>
    <router-link :to="{ path: '/Jamaica' }">Jamaica</router-link>
    <router-link :to="{ path: '/panama' }">Panama</router-link>
  </div>
</template>

<style scoped>
#nav .vue-school-active-link {
  color: red;
  border-bottom: 2px solid red;
}
</style>
