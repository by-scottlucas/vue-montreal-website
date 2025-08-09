<template>
  <main class="page-content">
    <Header />
    <HeroBanner />
    <Projects />
    <InfoCards />
    <CTABanner />
    <Footer />
  </main>
</template>

<script setup>
import { onMounted } from "vue";
import Header from "./components/Header.vue";
import HeroBanner from "./components/HeroBanner.vue";
import Projects from "./components/Projects.vue";
import InfoCards from "./components/InfoCards.vue";
import CTABanner from "./components/CTABanner.vue";
import Footer from "./components/Footer.vue";

onMounted(() => {
  document.title = "Montreal Construtora | Home";
});
</script>

<style scoped>
.page-content {
  @apply bg-gray-100 h-auto;
}
</style>
