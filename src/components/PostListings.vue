<script setup>
import { ref, computed, onMounted } from "vue";
import axios from "axios";
import { RouterLink } from "vue-router";

const articles = ref([]);

onMounted(async () => {
  try {
    const response = await axios.get(
      "/api/page?limit=10&page=1"
    );
    articles.value = response.data.results;
  } catch (error) {
    console.error("Error fetching articles", error);
  }
});
</script>

<template>
  <section class="flex flex-col p-5 lg:px-48 lg:py-11">
    <div
      v-for="article in articles"
      :key="article.id"
      class="bg-gray-100 p-5 rounded-3xl mb-10"
    >
      <h1 class="font-bold text-2xl mb-2">{{ article.title }}</h1>
      <p class="my-3">
        {{ article.content.substring(0, 570) + "..." }}
      </p>
      <RouterLink
        :to="'/post/' + article._id"
        class="hidden w-40 p-3 px-6 pt-2 text-white bg-sky-700 rounded-full baseline hover:bg-sky-500 md:block"
      >
        Czytaj więcej...
      </RouterLink>
    </div>
  </section>
</template>
