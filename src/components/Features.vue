<script setup>
import { ref, computed, onMounted } from "vue";
import { RouterLink } from "vue-router";
import axios from "axios";

const articles = ref([]);

onMounted(async () => {
  try {
    const response = await axios.get(
      "/api/blog/page?limit=10&page=1"
    );
    articles.value = response.data.results;
  } catch (error) {
    console.error("Error fetching articles", error);
  }
});
</script>

<template>
  <!-- Features Section -->
  <section id="features" class="bg-gray-50 py-10">
    <!-- Flex container -->
    <div
      class="container flex flex-col px-4 mx-auto space-y-12 md:space-y-0 md:flex-row"
    >
      <!-- Ostatnie wpisy -->

      <div
        v-for="(article, index) in articles.slice(0, 1)"
        :key="article.id"
        class="flex flex-col mx-12 mb-42 space-y-12 md:w-1/3"
      >
        <h2 class="max-w-md text-2xl font-bold text-center md:text-left">
          <a class="px-4 py-4 text-white rounded-full md:py-1 bg-sky-700"
            >{{ index + 1 }}.</a
          >
          {{ article.title }}
        </h2>
        <div class="max-w-sm text-left text-gray-800 md:text-left">
          <div
            class="w-28 px-2 text-gray-400 rounded-full md:py-1 bg-gray-200"
            >{{ article.date.slice(0, 10) }}</div
          >
          <div v-html="article.content.substring(0, 400) + '...'"></div>
          <RouterLink :to="'/post/' + article._id" class="hover:text-sky-600 font-bold"
            >Czytaj więcej</RouterLink
          >
        </div>
      </div>

      <!-- Numbered List -->
      <div class="flex flex-col space-y-8 md:w-1/2">
        <!-- List Item 1 -->
        <div
          v-for="(article, index) in articles.slice(1, 4)"
          :key="article.id"
          class="flex flex-col space-y-3 md:space-y-0 md:space-x-6 md:flex-row"
        >
          <!-- Heading -->
          <div class="rounded-full bg-sky-100 md:bg-transparent">
            <div class="flex items-center space-x-2">
              <div class="px-4 py-2 text-white rounded-full md:py-1 bg-sky-700">
                {{ index + 2 }}.
              </div>
              <h3 class="text-base font-bold md:mb-4 md:hidden">
                {{ article.title.substring(0, 30) + "..." }}
              </h3>
            </div>
          </div>

          <div>
            <h3 class="hidden mb-4 text-lg font-bold md:block">
              {{ article.title }}
            </h3>
            <p class="text-gray-800">
              <a
                class="px-2 text-gray-400 rounded-full md:py-1 bg-gray-200"
                >{{ article.date.slice(0, 10) }}</a
              >
              {{ article.content.slice(0, 200) + "..." }}
              <RouterLink :to="'/post/' + article._id" class="hover:text-sky-600 font-bold"
                >Czytaj więcej</RouterLink
              >
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
