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

      <div class="hero-banner__cards">
        <Card
          v-for="(card, index) in cards"
          :key="index"
          :icon="card.icon"
          :title="card.title"
          :description="card.description"
          :buttonIsVisible="true"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import heroImage from "../assets/hero-banner.png";
import Card from "./ui/Card.vue";
const heroAlt = "Imagem do banner principal da Montreal Construtora";

const cards = [
  {
    icon: "home",
    title: "Seu Sonho, Nossa Obra",
    description:
      "Construímos projetos que combinam qualidade, inovação e o seu estilo de vida.",
  },
  {
    icon: "sparkles",
    title: "Confiança e Experiência",
    description:
      "Entregamos obras residenciais e comerciais com excelência e compromisso.",
  },
  {
    icon: "pickaxe",
    title: "Do Projeto à Realidade",
    description:
      "Acompanhamos cada etapa para garantir qualidade, prazos e sua satisfação.",
  },
];
</script>

<style scoped>
.hero-banner {
  @apply lg:pt-4 min-h-max w-[95%] mx-auto;
}

.hero-banner__image {
  @apply bg-cover md:mx-auto w-full h-[260px] md:h-[380px] md:px-5 lg:h-[500px];
}

.hero-banner__content {
  @apply -mt-40 md:-mt-60 lg:-mt-80 text-white text-center w-full;
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

.hero-banner__cards {
  @apply md:max-w-[84%] lg:max-w-[74%] mx-auto hidden gap-8 md:flex justify-center md:mt-14 lg:mt-20;
}
</style>
