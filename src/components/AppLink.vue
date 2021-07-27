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
ref: to = ""
const isExternal = () => typeof to === "string" && to.startsWith("https")
</script>

<style lang="scss" scoped></style>
