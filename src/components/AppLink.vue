<template>
  <a
    v-if="isExternal"
    target="_blank"
    rel="noopener"
    class="external-link"
    :href="to"
    ><slot
  /></a>
  <router-link v-else v-bind="$props" class="internal-link"
    ><slot
  /></router-link>
</template>

<script setup>

import { RouterLink } from "vue-router"
defineProps({
  ...RouterLink.props,
})

const isExternal = () => typeof to === "string" && to.startsWith("http")
</script>

<style lang="scss" scoped></style>
