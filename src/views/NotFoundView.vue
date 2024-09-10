<script setup>
import { RouterLink } from "vue-router";
</script>

<template>
  <section class="text-center flex flex-col justify-center items-center h-96">
    <i class="pi pi-exclamation-triangle text-yellow-500 text-7xl mb-5"></i>
    <h1 class="text-6xl font-bold mb-4">404 Not Found</h1>
    <p class="text-xl mb-5">Ta strona nie istnieje</p>
    <RouterLink
      to="/"
      class="p-3 px-6 pt-2 text-white bg-sky-700 rounded-full baseline hover:bg-sky-500"
      >Powróć</RouterLink
    >
  </section>
</template>