<template>
  <section class="cta-banner">
    <img
      :src="ctaBanner"
      alt="Fale com um especialista"
      class="cta-banner__image"
      loading="lazy"
    />

    <div class="cta-banner__content">
      <p class="cta-banner__label">Dúvidas?</p>
      <p class="cta-banner__text">Converse com um</p>
      <p class="cta-banner__text">
        de nossos <strong>especialistas</strong>
      </p>

      <a href="#" class="cta-banner__button">
        <MessageCircle class="cta-banner__icon" />
        <span>Falar com um especialista</span>
      </a>
    </div>
  </section>
</template>

<script setup>
import { MessageCircle } from "lucide-vue-next";
import ctaBanner from "../assets/cta-contact-banner.png";
</script>

<style scoped>
.cta-banner {
  @apply relative mt-20 md:mt-32 px-4 md:px-10 lg:px-16 w-[95%] mx-auto;
}

.cta-banner__image {
  @apply bg-cover w-full h-[200px] md:h-[330px] lg:h-[350px];
}

.cta-banner__content {
  @apply absolute top-10 md:top-1/3 left-10 md:left-28 lg:left-32;
}

.cta-banner__label {
  @apply text-white text-sm md:text-lg font-bold;
}

.cta-banner__text {
  @apply text-white text-xl md:text-3xl font-medium;
}

.cta-banner__button {
  @apply flex items-center gap-2 mt-4 text-white font-medium bg-blue-600 hover:bg-blue-700 py-2 px-6 rounded-md w-max transition-all ease-in-out duration-300;
}

.cta-banner__icon {
  @apply w-5 h-5;
}
</style>