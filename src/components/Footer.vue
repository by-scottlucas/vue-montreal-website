<template>
  <footer class="footer">
    <div class="footer__top">
      <a href="#" class="footer__brand">
        <img :src="brandLogo" alt="Montreal Construtora" class="footer__logo" />
      </a>

      <div class="footer__socials">
        <a
          v-for="({ icon, url, label }, index) in socialIcons"
          :key="index"
          :href="url"
          class="footer__social-link"
          :aria-label="label"
        >
          <component :is="icon" :size="26" class="footer__social-icon" />
        </a>
      </div>
    </div>

    <div class="footer__middle">
      <div class="footer__newsletter">
        <p class="footer__text">Receba as novidades no seu e-mail!</p>
        <input
          type="email"
          placeholder="Seu melhor e-mail aqui"
          class="footer__input"
          aria-label="Digite seu e-mail"
        />
        <button type="submit" class="footer__button">Inscrever</button>
      </div>

      <div class="footer__contact">
        <p class="footer__section-title">Formas de Contato</p>
        <div class="footer__contact-list">
          <a
            v-for="({ icon, text, url }, index) in contactLinks"
            :key="index"
            :href="url"
            class="footer__contact-link"
          >
            <component :is="icon" :size="20" class="footer__icon" />
            <span>{{ text }}</span>
          </a>
        </div>
      </div>

      <div class="footer__links">
        <p class="footer__section-title">Links</p>
        <div class="footer__link-list">
          <a
            v-for="(link, index) in navLinks"
            :key="index"
            :href="link.url"
            class="footer__link"
          >
            {{ link.label }}
          </a>
        </div>
      </div>
    </div>

    <div class="footer__bottom">
      <span class="footer__copyright">
        Montreal Construtora. Todos os direitos reservados.
      </span>
    </div>
  </footer>
</template>

<script setup>
import {
  Facebook,
  Instagram,
  Linkedin,
  Mail,
  Phone,
  Youtube,
} from "lucide-vue-next";
import brandLogo from "../assets/montreal-logo.png";
import { defineComponent } from "vue";

defineComponent({
  name: "FooterComponent",
});

const socialIcons = [
  { icon: Linkedin, url: "#", label: "LinkedIn" },
  { icon: Instagram, url: "#", label: "Instagram" },
  { icon: Facebook, url: "#", label: "Facebook" },
  { icon: Youtube, url: "#", label: "YouTube" },
];

const contactLinks = [
  { icon: Phone, text: "(13) 99999-9999", url: "tel:+5513999999999" },
  {
    icon: Mail,
    text: "contato@montreal.com.br",
    url: "mailto:contato@montreal.com.br",
  },
];

const navLinks = [
  { label: "Lançamentos", url: "#" },
  { label: "Investidores", url: "#" },
  { label: "Dúvidas Frequentes", url: "#" },
  { label: "Contratar", url: "#" },
  { label: "Trabalhe conosco", url: "#" },
];
</script>

<style scoped>
.footer {
  @apply w-full mt-20 md:mt-32 px-4 py-6 md:px-10 lg:px-16 bg-white;
}

.footer__top {
  @apply flex justify-between items-center;
}

.footer__brand {
  @apply flex items-center;
}

.footer__logo {
  @apply w-[100px] xl:w-28;
}

.footer__socials {
  @apply flex gap-3;
}

.footer__social-icon {
  @apply text-blue-600;
}

.footer__middle {
  @apply grid grid-cols-1 md:grid-cols-3 gap-8 lg:gap-20 mt-10;
}

.footer__newsletter {
  @apply flex flex-col;
}

.footer__text {
  @apply text-black text-lg font-bold mb-3;
}

.footer__input {
  @apply px-3.5 py-2.5 border border-gray-300 rounded-md text-sm w-full lg:w-[340px] mb-2 outline-none focus:border-blue-700;
}

.footer__button {
  @apply w-max bg-blue-600 text-white text-sm px-8 py-2 rounded-md hover:bg-blue-700 transition-all;
}

.footer__contact {
  @apply flex flex-col;
}

.footer__section-title {
  @apply text-black text-lg font-bold mb-3;
}

.footer__contact-list {
  @apply flex flex-col gap-2 lg:gap-3;
}

.footer__contact-link {
  @apply flex items-center gap-2 text-gray-700 hover:text-blue-600 transition;
}

.footer__icon {
  @apply text-blue-600;
}

.footer__links {
  @apply flex flex-col;
}

.footer__link-list {
  @apply flex flex-col lg:grid lg:grid-cols-2 gap-2 lg:gap-3;
}

.footer__link {
  @apply text-gray-700 hover:text-blue-600 transition;
}

.footer__bottom {
  @apply mt-10 text-center border-t pt-4;
}

.footer__copyright {
  @apply text-sm text-gray-600;
}
</style>
