<script setup>
import { defineComponent, ref } from "vue";
import { Menu } from "lucide-vue-next";
import logo from "../assets/montreal-logo.png";

defineComponent({
  name: "HeaderComponent",
});

const menuIsOpen = ref(false);

const navLinks = [
  { title: "Home", link: "#" },
  { title: "Institucional", link: "#" },
  { title: "Empreendimentos", link: "#" },
  { title: "Contato", link: "#" },
];

function toggleMenu() {
  menuIsOpen.value = !menuIsOpen.value;
}
</script>

<template>
  <nav class="header">
    <a href="#" class="header__brand">
      <img
        :src="logo"
        alt="Montreal Construtora"
        class="header__logo"
        loading="eager"
      />
    </a>

    <button
      type="button"
      @click="toggleMenu"
      class="header__burger-button"
      aria-controls="navbar"
      aria-label="Menu Button"
      :aria-expanded="menuIsOpen ? 'true' : 'false'"
    >
      <Menu :size="26" />
    </button>

    <div class="header__actions">
      <div
        :class="[
          'header__items',
          menuIsOpen ? 'header__items--open' : 'header__items--close',
        ]"
        id="navbar"
      >
        <ul class="header__list">
          <li v-for="(item, index) in navLinks" :key="index">
            <a
              :href="item.link"
              class="header__link"
              :class="
                item.title === 'Contato'
                  ? 'header__link--contact'
                  : 'header__link--default'
              "
            >
              {{ item.title }}
            </a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.header {
  @apply bg-white flex flex-wrap lg:text-start items-center justify-between mx-auto p-4 xl:px-12;
}

.header__brand {
  @apply flex items-center;
}

.header__logo {
  @apply w-[90px] xl:w-24;
}

.header__burger-button {
  @apply inline-flex items-center p-2 justify-center text-black rounded-md lg:hidden border;
}

.header__actions {
  @apply w-full lg:w-auto lg:gap-3 lg:flex lg:items-center lg:justify-between lg:flex-row-reverse;
}

.header__items {
  @apply overflow-hidden text-center w-full lg:w-auto transition-all duration-500 ease-in-out lg:flex lg:opacity-100 lg:max-h-full;
}

.header__items--open {
  @apply max-h-96 opacity-100;
}

.header__items--close {
  @apply max-h-0 opacity-0 lg:opacity-100 lg:max-h-full;
}

.header__list {
  @apply gap-2 lg:gap-1 flex flex-col p-4 md:p-0 lg:flex-row lg:space-x-4 md:mt-0 md:border-0 md:bg-white;
}

.header__link {
  @apply block py-2.5 lg:px-2.5 lg:py-1 text-lg xl:text-[15px] font-medium transition-all duration-300 ease-in-out;
}

.header__link--default {
  @apply hover:text-blue-600;
}

.header__link--contact {
  @apply text-white rounded-full px-7 bg-blue-600 hover:bg-blue-700;
}
</style>
