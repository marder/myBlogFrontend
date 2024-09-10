<script setup>
import photo from "@/assets/img/main_md_s2.png";
</script>

<template>
  <!-- Hero Section -->
  <section id="hero" class="">
    <!-- Flex Container -->
    <div
      class="container flex flex-col-reverse items-center px-6 mx-auto pt-10 space-y-0 md:space-y-0 md:flex-row"
    >
      <!-- Left item -->
      <div class="flex flex-col p-6 mb-42 space-y-12 md:w-1/2">
        <h1
          class="max-w-md text-4xl font-bold text-center md:text-5xl md:text-left"
        >
          Zrozum, że debilem trzeba się urodzić.
        </h1>
        <p class="max-w-sm text-center text-gray-800 md:text-left">
          Na mistrzowskie umiejetności trzeba sobie zapracować. Aby coś
          osiągnąć, trzeba wiele wycierpieć. Jednak debilem trzeba się urodzić.
        </p>
        <div class="flex justify-center md:justify-start">
          <a
            href="#"
            class="hidden p-3 px-6 pt-2 text-white bg-sky-700 rounded-full baseline hover:bg-sky-500 md:block"
            >Zajrzyj łaskawie na bloga</a
          >
        </div>
      </div>
      <!-- Image -->
      <div class="md:w-3/4 pt-10">
        <img :src="photo" alt="" />
      </div>
    </div>
  </section>
</template>
