<script setup>
import { ref, computed, onMounted } from "vue";
import axios from "axios";
import { RouterLink } from "vue-router";

const articles = ref([]);

onMounted(async () => {
  try {
    const response = await axios.get("/api/blog/");
    articles.value = response.data;
  } catch (error) {
    console.error("Error fetching articles", error);
  }
});
</script>

<template>
  <section class="bg-gray-100 p-4">
    <h2 class="text-xl font-bold text-gray-800 mb-4">Ostatnie wpisy</h2>
    <div
      v-for="(article, index) in articles.slice(0, 8)"
      :key="article._id"
      class="mb-2"
    >
      <a
        :href="'/post/' + article._id"
        class="text-gray-700 hover:text-gray-900"
        >{{ index + 1 }}. {{ article.title }}</a
      >
    </div>
  </section>
</template>