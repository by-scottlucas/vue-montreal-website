<template>
  <section class="hero-banner" role="banner" aria-label="Seção principal">
    <img
      :src="heroImage"
      :alt="heroAlt"
      class="hero-banner__image"
      loading="lazy"
    />

    <div class="hero-banner__content">
      <div class="hero-banner__text-group">
        <p class="hero-banner__text">Invista agora mesmo em um imóvel</p>
        <p class="hero-banner__text">Moderno e Futurista</p>
      </div>

      <a href="#" class="hero-banner__button">Ver Projetos</a>
    </div>
  </section>
</template>

<script setup>
import heroImage from "../assets/hero-banner.png";
const heroAlt = "Imagem do banner principal da Montreal Construtora";
</script>

<style scoped>
.hero-banner {
  @apply relative h-[260px] md:h-[340px] lg:h-[550px];
}

.hero-banner__image {
  @apply h-full bg-cover md:mx-auto w-max;
}

.hero-banner__content {
  @apply absolute top-1/3 lg:translate-y-1/3 text-white text-center w-full;
}

.hero-banner__text-group {
  @apply flex flex-col md:gap-1.5 mb-3.5 md:mb-8;
}

.hero-banner__text {
  @apply text-xl md:text-3xl lg:text-4xl font-bold;
}

.hero-banner__button {
  @apply bg-blue-600 hover:bg-blue-700 py-2.5 md:py-3 px-6 md:px-8 rounded-md text-sm md:text-base transition-all ease-in-out duration-300;
}
</style>
