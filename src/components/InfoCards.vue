<template>
  <section class="info-section">
    <div class="info-section__grid">
      <Card
        v-for="(card, index) in cards"
        :key="index"
        :icon="card.icon"
        :title="card.title"
        :description="card.description"
      />
    </div>
  </section>
</template>

<script setup>
import Card from "./ui/Card.vue";

const cards = [
  {
    icon: "pickaxe",
    title: "Status de Obras",
    description:
      "Acompanhe o andamento das obras do apartamento dos seus sonhos, atualizado mensalmente com fotos.",
  },
  {
    icon: "home",
    title: "Ofereça Seu Terreno",
    description:
      "Estamos em busca de áreas com negociação para desenvolvimento de novos projetos.",
  },
  {
    icon: "globe",
    title: "Blog",
    description:
      "Tudo sobre mercado imobiliário, dicas de decoração, arquitetura, notícias, bem estar e economia.",
  },
];
</script>

<style scoped>
.info-section {
  @apply mt-20 md:mt-32 px-4 md:px-10 lg:px-16 w-[95%] mx-auto;
}

.info-section__grid {
  @apply grid gap-6 lg:gap-8 grid-cols-2 md:grid-cols-3;
}
</style>
