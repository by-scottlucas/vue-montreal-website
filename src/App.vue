<template>
  <Header />
  <main class="page-content">
    <HeroBanner />
  </main>
</template>

<script setup>
import { onMounted } from "vue";
import Header from "./components/Header.vue";
import HeroBanner from "./components/HeroBanner.vue";

onMounted(() => {
  document.title = "Montreal Construtora | Home";
});
</script>

<style scoped>
.page-content {
  @apply bg-gray-100 lg:p-4 h-auto;
}
</style>
