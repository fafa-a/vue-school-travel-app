<template>
  <div id="nav">
    <RouterLink id="logo" to="/">Vue School Travel App</RouterLink>
    <RouterLink
      v-for="destination in destinations"
      :key="destination.id"
      :to="{
        name: 'destination.show',
        params: { id: destination.id, slug: destination.slug },
      }"
    >
      {{ destination.name }}
    </RouterLink>
    <RouterLink :to="{ name: 'protected' }">Dashboard</RouterLink>
    <AppLink to="https://vueschool.io">Vue School</AppLink>
  </div>
</template>
<script setup>
import sourceData from "@/data.json"

const { destinations } = sourceData
</script>
