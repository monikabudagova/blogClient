<template>
<main class="w-full lg:px-40">
        <div class="ns_post">
            <div class="h-80 rounded-2xl my-4 bg-fixed bg-[length:100%_600px]" :style="'background-image: url('+base_url+post.img.url+')'"></div>
            <h1 class="relative text-4xl">{{ post.title }} <Share /></h1>
            <p class="opacity-40">{{ post.views }} просмотров</p>
            <div v-html="mark"></div>
        </div>
    </main>
  </template>
  
  
  <script setup>
    const base_url = "https://4ccc2241e457.vps.myjino.ru"
    const { id } = useRoute().params
    const api = await $fetch(`https://4ccc2241e457.vps.myjino.ru/api/posts/${id}?populate=*`)
    const post = api.data
  </script>