<template>
  <Header />
</template>

<script setup>
import { onMounted } from "vue";
import Header from "./components/Header.vue";

onMounted(() => {
  document.title = "Montreal Construtora | Home";
});
</script>