<template>
  <section class="destination">
    <h1>{{ destination.name }}</h1>
    <div class="destination-details">
      <img :src="`/images/${destination.image}`" :alt="destination.name" />
      <p>{{ destination.description }}</p>
    </div>
  </section>
</template>

<script setup>
import { computed, onMounted, onUpdated } from "@vue/runtime-core"
import { useRoute } from "vue-router"

const route = useRoute()
ref: destination = {}
ref: destinationId = ""

destinationId = computed(() => parseInt(route.params.id))

const initData = async () => {
  const res = await fetch(
    `https://travel-dummy-api.netlify.app/${route.params.slug}`
  )
  destination = await res.json()
}

onMounted(() => {
  initData()
})

// onUpdated(() => {
//   initData()
// })
</script>

<style lang="scss" scoped></style>
