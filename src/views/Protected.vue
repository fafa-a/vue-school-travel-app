<template>
  <div>
    <h1>Greetings, {{ username }}</h1>
    <button @click="logout">Logout</button>
  </div>
</template>
<script setup>
import { useRouter } from "vue-router"

ref: username = window.user

const router = useRouter()

const logout = () => {
  username = null
  router.push({ name: "home" })
}
</script>
