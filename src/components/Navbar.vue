<script setup>
import logo from "@/assets/img/logo.svg";
import { RouterLink, useRoute } from "vue-router";

const isActiveLink = (routePath) => {
  const route = useRoute();
  return route.path === routePath;
};
</script>

<template>
  <!-- Navbar begin -->
  <nav class="relative container mx-auto p-6">
    <!-- Flex container begin -->
    <div class="flex items-center justify-between">
      <!-- Logo -->
      <div class="pt-2 pl-12">
        <RouterLink to="/" class="hover:text-sky-600"
          ><img :src="logo" alt=""
        /></RouterLink>
      </div>
      <!-- Logo end -->
      <!-- Menu items -->
      <div class="hidden md:flex space-x-12">
        <RouterLink
          to="/"
          :class="[isActiveLink('/') ? 'text-sky-700' : 'hover:text-sky-300']"
          >Główna</RouterLink
        >
        <RouterLink
          to="/posts"
          :class="[
            isActiveLink('/posts') ? 'text-sky-700' : 'hover:text-sky-300',
          ]"
          >Blog</RouterLink
        >
        <RouterLink
          to="/about"
          :class="[
            isActiveLink('/about') ? 'text-sky-700' : 'hover:text-sky-300',
          ]"
          >O mnie</RouterLink
        >
      </div>
      <!-- Button -->
      <a
        href="#"
        class="hidden p-3 px-6 pt-2 text-white bg-sky-700 rounded-full baseline hover:bg-sky-500 md:block"
        >Zajrzyj na bloga</a
      >
      <!-- Hamburger Icon -->
      <button
        id="menu-btn"
        class="block hamburger md:hidden focus:outline-none"
      >
        <span class="hamburger-top"></span>
        <span class="hamburger-middle"></span>
        <span class="hamburger-bottom"></span>
      </button>
    </div>
    <!-- Mobile Menu -->
    <div class="md:hidden">
      <div
        id="menu"
        class="absolute flex-col items-center hidden self-end py-8 mt-10 space-y-6 font-bold bg-white sm:w-auto sm:self-center left-6 right-6 drop-shadow-md"
      >
        <a href="#" class="hover:text-sky-600">Główna</a>
        <a href="#" class="hover:text-sky-600">Blog</a>
        <a href="#" class="hover:text-sky-600">O mnie</a>
      </div>
    </div>
  </nav>
  <!-- Navbar end -->
</template>
