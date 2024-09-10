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
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Facere
          praesentium explicabo quas impedit itaque necessitatibus doloremque
          odit autem nostrum rerum corrupti voluptatem, dicta quam assumenda,
          reprehenderit aliquid eligendi ad deleniti, ipsam accusantium. Vel
          facilis voluptas tempora quae exercitationem enim quod! Illo officia
          nulla, perferendis, cumque eaque sunt perspiciatis, ab consectetur
          beatae hic fugit quasi deleniti obcaecati laudantium ad est qui
          veritatis nam eius possimus itaque? Amet.
        </p>
      </div>
      <!-- Image -->
      <div class="md:w-3/4 pt-10">
        <img :src="photo" alt="" />
      </div>
    </div>
  </section>
</template>