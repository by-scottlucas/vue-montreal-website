<template>
  <div class="card">
    <div>
      <component :size="55" :is="resolvedIcon" class="card__icon" />

      <h2 class="card__title">{{ title }}</h2>
      <p class="card__description">{{ description }}</p>
    </div>

    <a v-if="buttonIsVisible" href="#" class="card__button">Saiba Mais</a>
  </div>
</template>

<script>
import { Home, Pickaxe, Sparkles } from "lucide-vue-next";

export default {
  name: "CardComponent",

  props: {
    icon: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    buttonIsVisible: {
      type: Boolean,
      default: false,
    },
  },

  computed: {
    resolvedIcon() {
      const iconMap = {
        home: Home,
        pickaxe: Pickaxe,
        sparkles: Sparkles,
      };
      return iconMap[this.icon] || null;
    },
  },
};
</script>

<style scoped>
.card {
  @apply bg-white rounded-md shadow-md text-center gap-12 flex flex-col justify-between w-[190px] lg:w-[300px] p-2 lg:px-5 lg:py-8;
}

.card__icon {
  @apply mx-auto mb-2 lg:mb-4 text-blue-600;
}

.card__title {
  @apply text-base lg:text-xl font-bold mb-2 text-black;
}

.card__description {
  @apply text-sm lg:text-base text-justify text-gray-600;
}

.card__button {
  @apply block bg-blue-600 hover:bg-blue-700 text-white py-1.5 lg:py-2.5 px-4 rounded transition;
}
</style>
