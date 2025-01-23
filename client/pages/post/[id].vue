<template>
  <main class="w-full lg:px-40">
      <!-- хлебные крошки -->
      <nav class="flex" aria-label="Breadcrumb" v-if="post">
          <ol class="inline-flex items-center space-x-1 md:space-x-2 rtl:space-x-reverse">
              <li class="inline-flex items-center">
                  <NuxtLink to="/blog"
                      class="inline-flex items-center text-sm font-medium text-gray-700 hover:text-blue-600 dark:text-gray-400 dark:hover:text-white">
                      <svg class="w-3 h-3 me-2.5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 20">
                          <path d="m19.707 9.293-2-2-7-7a1 1 0 0 0-1.414 0l-7 7-2 2a1 1 0 0 0 1.414 1.414L2 10.414V18a2 2 0 0 0 2 2h3a1 1 0 0 0 1-1v-4a1 1 0 1 1 2 0v4a1 1 0 0 0 1 1h3a2 2 0 0 0 2-2v-7.586l.293.293a1 1 0 0 0 1.414-1.414Z" />
                      </svg>
                      Блог
                  </NuxtLink>
              </li>
              <li>
                  <div class="flex items-center">
                      <svg class="rtl:rotate-180 w-3 h-3 text-gray-400 mx-1" aria-hidden="true"
                          xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 6 10">
                          <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                              d="m1 9 4-4-4-4" />
                      </svg>
                      <NuxtLink :to="'/category/' + post.categories?.[0].documentId"
                          class="ms-1 text-sm font-medium text-gray-700 hover:text-blue-600 md:ms-2 dark:text-gray-400 dark:hover:text-white">
                          {{ post.categories?.[0]?.title || 'Без категории' }}
                          
                      </NuxtLink>
                  </div>
              </li>
              <li aria-current="page">
                  <div class="flex items-center">
                      <svg class="rtl:rotate-180 w-3 h-3 text-gray-400 mx-1" aria-hidden="true"
                          xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 6 10">
                          <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                              d="m1 9 4-4-4-4" />
                      </svg>
                      <span class="ms-1 text-sm font-medium text-gray-500 md:ms-2 dark:text-gray-400">
                          <strong>{{ post.title }}</strong>
                      </span>
                  </div>
              </li>
          </ol>
      </nav>
      <div class="ns_post text-black dark:text-white" v-if="post">
          <div class="h-80 rounded-2xl my-4 bg-fixed bg-[length:100%_600px]" :style="'background-image: url(' + (post.img?.url ? base_url + post.img.url : '') + ')'"></div>
          <h1 class="relative text-4xl">
              {{ post.title }}
              <Share />
          </h1>
          <p class="opacity-40">{{ formatDate(post.publishedAt?.substring(0, 10)) }}</p>
          <div v-html="mark"></div>
      </div>
      <p v-else-if="errorMessage" class="text-center text-red-500">
          {{ errorMessage }}
      </p>
      <p v-else class="text-center text-gray-500">Загрузка данных...</p>
  </main>
</template>

<script setup>
import MarkdownIt from "markdown-it";
import { ref, onMounted, computed } from "vue";

const markdown = new MarkdownIt();
const post = ref(null);
const config = ref(null);
const errorMessage = ref("");
const base_url = 'https://4ccc2241e457.vps.myjino.ru';
const { id } = useRoute().params;

// Загрузка поста
const fetchPost = async () => {
  try {
      const api = await $fetch(`${base_url}/api/posts/${id}?populate=*`);
      post.value = api.data || {};
  } catch (error) {
      console.error("Ошибка загрузки данных поста:", error);
      errorMessage.value = "Не удалось загрузить данные поста. Попробуйте позже.";
  }
};

// Загрузка конфигурации
const fetchConfig = async () => {
  try {
      const apiConfig = await $fetch(`${base_url}/api/config?populate=*`);
      config.value = apiConfig.data;
  } catch (error) {
      console.error("Ошибка загрузки конфигурации:", error);
  }
};

// Markdown контент
const mark = computed(() => post.value ? markdown.render(post.value.body || "") : "");

// Мета-данные
useHead(computed(() => ({
  title: post.value && config.value ? `${post.value.title} - ${config.value.title}` : "Загрузка...",
})));

// Форматирование даты
function formatDate(dateString) {
  if (dateString) {
      const date = new Date(Date.parse(dateString));
      const day = date.getDate();
      const monthNames = [
          'января', 'февраля', 'марта', 'апреля', 'мая', 'июня',
          'июля', 'августа', 'сентября', 'октября', 'ноября', 'декабря'
      ];
      return `${day} ${monthNames[date.getMonth()]}`;
  }
  return '';
}

// Загрузка данных
onMounted(async () => {
  await Promise.all([fetchPost(), fetchConfig()]);
});
</script>