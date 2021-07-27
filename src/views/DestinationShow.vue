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
import sourceData from "@/data.json"

const route = useRoute()
ref: destination = {}
ref: destinationId = ""

destinationId = computed(() => parseInt(route.params.id))

const initDestination = () => {
  destination = sourceData.destinations.find(
    (dest) => dest.id === destinationId.value
  )
}
onMounted(() => {
  initDestination()
})

// onUpdated(() => {
//   initDestination()
// })

</script>

<style lang="scss" scoped></style>
