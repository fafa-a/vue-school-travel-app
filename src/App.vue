<template>
  <TheNavigation />
  <div class="container">
    <router-view v-slot="{ Component }">
      <transition name="fade" mode="out-in">
        <component :is="Component" :key="$route.path"></component>
      </transition>
    </router-view>
  </div>
</template>

<script setup>
import TheNavigation from "@/components/TheNavigation.vue"
</script>
<style lang="css">
.fade-enter-active,
.fade-leave-active {
  transition: all 0.3s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
  transform: translateX(-30%);
}
</style>
