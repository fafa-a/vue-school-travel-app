<template>
  <section>
    <h1>{{ experience.name }}</h1>
    <img :src="`/images/${experience.image}`" :alt="experience.name" />
    <p>{{ experience.description }}</p>
  </section>
</template>
<script setup>
import sourceData from "@/data.json"
import { computed, onMounted } from "@vue/runtime-core"

ref: destination = {}
ref: experience = {}

const props = defineProps({
  id: {
    type: Number,
    required: true,
  },
  experienceSlug: {
    type: String,
    required: true,
  },
})
const findDestination = () => {
  destination = sourceData.destinations.find((dest) => dest.id === props.id)
}
const findExperience = () => {
  experience = destination.experiences.find(
    (exp) => exp.slug === props.experienceSlug
  )
}

onMounted(() => {
  findDestination()
  findExperience()
})
</script>
