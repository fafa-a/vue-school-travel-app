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
import sourceData from "@/data.json"

ref: destination = {}

const props = defineProps({
  id: {
    type: Number,
    required: true,
  },
})

const initDestination = () => {
  destination = sourceData.destinations.find((dest) => dest.id === props.id)
}
onMounted(() => {
  initDestination()
})

// onUpdated(() => {
//   initDestination()
// })
</script>

<style lang="scss" scoped></style>
