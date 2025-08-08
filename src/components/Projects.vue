<template>
  <section class="projects">
    <div class="projects__header">
      <div class="projects__divider"></div>
      <h2 class="projects__title">Projetos em Destaque</h2>
    </div>

    <div class="projects__grid">
      <img
        v-for="(project, index) in projects"
        :key="index"
        :src="project.image"
        :alt="project.alt"
        class="projects__image"
        loading="lazy"
      />
    </div>
  </section>
</template>

<script setup>
import { defineComponent } from "vue";
import project1 from "../assets/image-0.png";
import project2 from "../assets/image-1.png";
import project3 from "../assets/image-2.png";
import project4 from "../assets/image-3.png";
import project5 from "../assets/image-4.png";
import project6 from "../assets/image-5.png";

defineComponent({
  name: "ProjectsComponent",
});

const projects = [
  { image: project1, alt: "Projeto 1" },
  { image: project2, alt: "Projeto 2" },
  { image: project3, alt: "Projeto 3" },
  { image: project4, alt: "Projeto 4" },
  { image: project5, alt: "Projeto 5" },
  { image: project6, alt: "Projeto 6" },
];
</script>

<style scoped>
.projects {
  @apply mt-32 px-4 md:px-10 lg:px-16 w-[95%] mx-auto;
}

.projects__header {
  @apply mb-4 md:mb-8;
}

.projects__divider {
  @apply h-1 w-28 bg-black mb-2 md:mb-4;
}

.projects__title {
  @apply text-2xl md:text-3xl font-bold;
}

.projects__grid {
  @apply grid gap-6 grid-cols-2 md:grid-cols-3;
}

.projects__image {
  @apply w-full object-cover;
}
</style>
