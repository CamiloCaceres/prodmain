<script setup lang="ts">
import { HamburgerMenuIcon } from '@radix-icons/vue';

const links = reactive([
  {
    text: "Sobre nosotros",
    to: "/nosotros",
  },
  {
    text: "Contáctanos",
    to: "/contacto",
  },
  {
    text: "Servicios",
    to: "/servicios",
  },
]);
</script>

<template>
  <nav class="flex justify-between sm:justify-around py-4 px-8 shadow-md items-center">
    <h1>Prodmain</h1>
    <div class="sm:flex items-center space-x-4 hidden">
      <div v-for="(link, index) in links" :key="index">
        <Button variant="link">{{ link.text }}</Button>
      </div>
    </div>

    <Button variant="outline" class="sm:hidden">
      <HamburgerMenuIcon class="w-4 h-4"/>
    </Button>
  </nav>
</template>
