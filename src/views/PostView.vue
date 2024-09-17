<script setup>
import { ref, computed, onMounted } from "vue";
import { useRoute, RouterLink } from "vue-router";
import axios from "axios";

import LastPosts from "@/components/LastPosts.vue";

const article = ref([]);

const route = useRoute();
const postId = route.params.id;

onMounted(async () => {
  try {
    const response = await axios.get(`https://xder.bieda.it/blog/blog/${postId}`);
    article.value = response.data;
    console.log(article.value.title);
  } catch (error) {
    console.error("Error fetching article", error);
  }
});

const convertedDate = computed(() => {
  let dd = String(article.value.date).slice(8, 10);
  let mm = String(article.value.date).slice(5, 7);
  let yyyy = String(article.value.date).slice(0, 4);
  let month = "";

  if (mm === "01") {
    month = "stycznia";
  }
  if (mm === "02") {
    month = "lutego";
  }
  if (mm === "03") {
    month = "marca";
  }
  if (mm === "04") {
    month = "kwietnia";
  }
  if (mm === "05") {
    month = "maja";
  }
  if (mm === "06") {
    month = "czerwca";
  }
  if (mm === "07") {
    month = "lipca";
  }
  if (mm === "08") {
    month = "sierpnia";
  }
  if (mm === "09") {
    month = "września";
  }
  if (mm === "10") {
    month = "października";
  }
  if (mm === "11") {
    month = "listopada";
  }
  if (mm === "12") {
    month = "grudnia";
  }

  return dd + " " + month + " " + yyyy;
});
</script>

<template>
  <section class="flex flex-col">
    <div class="bg-gray-100 py-8">
      <div class="container mx-auto px-8">
        <h1 class="text-4xl font-bold text-gray-800 mb-2">
          {{ article.title }}
        </h1>
        <p class="text-gray-600">Opublikowano {{ convertedDate }} r.</p>
      </div>
    </div>
    <div class="bg-white py-8">
      <div class="container mx-auto px-4 flex flex-col md:flex-row">
        <div class="w-full md:w-3/4 px-4">
          <img
            src="https://images.unsplash.com/photo-1506157786151-b8491531f063"
            alt="Blog Featured Image"
            class="mb-8"
          />
          <div class="prose max-w-none">
            <div v-html="article.content" class="mb-5"></div>
          </div>
        </div>
        <div class="w-full md:w-1/4 px-4">
          <LastPosts />
        </div>
      </div>
    </div>
  </section>
</template>
