<template>
  <main>
    <div class="grid frid-cols-1 sm:grid-cols2 lg:grid-cols-4 gap-4 mb-4">
      <article v-for="post in displayedPosts" :key="post.id" class="max-w-sm bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700">
          <NuxtLink class="block overflow-hidden" :to="'/post/' + post.documentId">
              <img class="rounded-t-lg" :src="base_url+post.img.url" :alt=post.img.alternativeText />
          </NuxtLink>
          <div class="p-5">
              <NuxtLink :to="'/post/' + post.documentId">
                  <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">{{ post.title }}</h5>
              </NuxtLink>
              <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">{{ post.desc }}</p>
              <NuxtLink :to="'/post/' + post.documentId" class="inline-flex items-center px-3 py-2 text-sm font-medium text-center text-white bg-violet-600 rounded-lg hover:bg-violet-500 focus:ring-4 focus:outline-none focus:ring-violet-300 dark:bg-violet-600 dark:hover:bg-indigo-700 dark:focus:ring-indigo-800">
                  Подробнее
                  <svg class="rtl:rotate-180 w-3.5 h-3.5 ms-2" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
                      <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 5h12m0 0L9 1m4 4L9 9"/>
                  </svg>
              </NuxtLink>
          </div>
      </article>
    </div>
    <button v-if="!(displayedPosts.length === posts.length)" @click="loadMore" type="button" class="w-full text-blue-700 hover:text-white border border-indigo-700 hover:bg-indigo-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center me-2 mb-2 dark:border-indigo-500 dark:text-indigo-500 dark:hover:text-white dark:hover:bg-indigo-500 dark:focus:ring-indigo-800">Смотреть еще</button>
  </main>

</template>


<script setup>
const base_url = "https://4ccc2241e457.vps.myjino.ru"
const api = await $fetch('https://4ccc2241e457.vps.myjino.ru/api/posts?populate=*')
const posts = api.data
const displayedPosts = ref(posts.slice()); // Первые 3 поста
const loadMore = () => {
  displayedPosts.value = displayedPosts.value.concat(posts.slice(displayedPosts.value.length, displayedPosts.value.length + 1));
};
</script>

<style scoped>

main{
    color: #000000;
}
h2{
    display: flex;
    justify-content: center;
}
</style>



