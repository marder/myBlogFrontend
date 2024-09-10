<script setup>
import white_logo from "@/assets/img/logo-white.svg";
import icon_facebook from "@/assets/img/icon-facebook.svg";
import icon_youtube from "@/assets/img/icon-youtube.svg";
import icon_twitter from "@/assets/img/icon-twitter.svg";
import icon_instagram from "@/assets/img/icon-instagram.svg";
import icon_pinterest from "@/assets/img/icon-pinterest.svg";
</script>

<template>
  <!-- Footer -->
  <footer class="bg-gray-900">
    <!-- Flex Container -->
    <div
      class="container flex flex-col-reverse justify-between px-12 py-10 mx-auto space-y-8 md:flex-row md:space-y-0"
    >
      <!-- Logo and social links container -->
      <div
        class="flex flex-col-reverse items-center justify-between space-y-12 md:flex-col md:space-y-0 md:items-start"
      >
        <div class="mx-auto my-6 text-center text-white md:hidden">
          Copyright &copy; 2024, All Rights Reserved
        </div>
        <!-- Logo -->
        <div>
          <img :src="white_logo" alt="" />
        </div>
        <!-- Social Links Container -->
        <div class="flex justify-center space-x-4">
          <!-- Link 1 -->
          <a href="#">
            <img :src="icon_facebook" alt="" class="h-8" />
          </a>
          <!-- Link 2 -->
          <a href="#">
            <img :src="icon_youtube" alt="" class="h-8" />
          </a>
          <!-- Link 3 -->
          <a href="#">
            <img :src="icon_twitter" alt="" class="h-8" />
          </a>
          <!-- Link 4 -->
          <a href="#">
            <img :src="icon_pinterest" alt="" class="h-8" />
          </a>
          <!-- Link 5 -->
          <a href="#">
            <img :src="icon_instagram" alt="" class="h-8" />
          </a>
        </div>
      </div>
      <!-- List Container -->
      <div class="flex justify-around space-x-32">
        <div class="flex flex-col space-y-3 text-white">
          <a href="#" class="hover:text-brightRed">Home</a>
          <a href="#" class="hover:text-brightRed">Pricing</a>
          <a href="#" class="hover:text-brightRed">Products</a>
          <a href="#" class="hover:text-brightRed">About</a>
        </div>
        <div class="flex flex-col space-y-3 text-white">
          <a href="#" class="hover:text-brightRed">Careers</a>
          <a href="#" class="hover:text-brightRed">Community</a>
          <a href="#" class="hover:text-brightRed">Privacy Policy</a>
        </div>
      </div>

      <!-- Input Container -->
      <div class="flex flex-col justify-between">
        <form>
          <div class="flex space-x-3">
            <input
              type="text"
              class="flex-1 px-4 rounded-full focus:outline-none"
              placeholder="Updated in your inbox"
            />
            <button
              class="px-6 py-2 text-gray-900 rounded-full bg-white hover:bg-sky-200 focus:outline-none"
            >
              Go
            </button>
          </div>
        </form>
        <div class="hidden text-white md:block">
          Copyright &copy; 2024, All Rights Reserved
        </div>
      </div>
    </div>
  </footer>
</template>
