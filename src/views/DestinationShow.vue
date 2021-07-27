<template>
  <section class="destination">
    <h1>{{ destination.name }}</h1>
    <div class="destination-details">
      <img :src="`/images/${destination.image}`" :alt="destination.name" />
      <p>{{ destination.description }}</p>
    </div>
  </section>
  <section class="experiences">
    <h2>Top experiences in {{ destination.name }}</h2>
    <div class="cards">
      <router-link
        v-for="experience in destination.experiences"
        :key="experience.slug"
        :to="{
          name: 'experience.show',
          params: { experienceSlug: experience.slug },
        }"
      >
        <ExperienceCard :experience="experience" />
      </router-link>
    </div>
    <RouterView />
  </section>
</template>

<script setup>
import { computed, onMounted, onUpdated } from "@vue/runtime-core"
import sourceData from "@/data.json"
import ExperienceCard from "@/components/ExperienceCard.vue"

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
</script>

<style lang="scss" scoped></style>
