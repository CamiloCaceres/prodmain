<script setup lang="ts">
import { HamburgerMenuIcon } from "@radix-icons/vue";

import { Home, Info, Briefcase, Mail, ChevronLeft } from "lucide-vue-next";

const links = ref([
  { text: "Sobre nosotros", to: "/nosotros", icon: Info },
  { text: "Servicios", to: "/servicios", icon: Briefcase },
  { text: "Contacto", to: "/contacto", icon: Mail },
]);
</script>

<template>
  <nav
    class="flex justify-between sm:justify-around p-5 shadow-md items-center"
  >
    <Sheet>
      <SheetTrigger class="sm:hidden">
        <Button variant="outline">
          <HamburgerMenuIcon class="w-4 h-4" /> </Button
      ></SheetTrigger>
      <SheetContent side="left">
        <SheetHeader class="mb-12 mx-auto">
          <NuxtLink to="/">
            <img src="/Logo.webp" alt="Prodmain" class="h-12 w-auto" />
          </NuxtLink>
        </SheetHeader>
        <div class="flex flex-col justify-center items-start space-y-4">
          <div v-for="(link, index) in links" :key="index">
            <NuxtLink :to="link.to">
              <Button class="text-md" variant="link"
                >{{ link.text }}
                <component :is="link.icon" class="w-5 h-5 ml-2"
              /></Button>
            </NuxtLink>
          </div>
        </div>
      </SheetContent>
    </Sheet>
    <NuxtLink to="/">
      <img src="/Logo.webp" alt="Prodmain" class="h-12 w-auto" />
    </NuxtLink>
    <div class="hidden sm:flex items-center space-x-4">
      <div v-for="(link, index) in links" :key="index">
        <NuxtLink :to="link.to">
          <Button class="text-md" variant="link">{{ link.text }}</Button>
        </NuxtLink>
      </div>
    </div>
  </nav>
</template>
