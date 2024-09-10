<script setup>
import { onMounted } from "vue";

import Navbar from "@/components/Navbar.vue";
import Footer from "@/components/Footer.vue";
import { RouterView } from "vue-router";

//Hamburger script
onMounted(() => {
  const btn = document.getElementById("menu-btn");
  const nav = document.getElementById("menu");

  btn.addEventListener("click", () => {
    btn.classList.toggle("open");
    nav.classList.toggle("flex");
    nav.classList.toggle("hidden");
  });
});
</script>

<template>
  <Navbar />
  <RouterView />
  <Footer />
</template>
