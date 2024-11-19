<template>
    <NuxtLoadingIndicator throttle="0"/>
    <Navbar />
    <NuxtPage />
    <Up />
    <Footer />
  </template>
  
  <script setup>
    const base = 'http://localhost:1337' 
    const api = await $fetch(`${base}/api/config?populate=*`)
    const config = api.data
  
    useHead({
      title: config.title,
      meta: [
        { name: 'description', content: config.desc },
        { name: 'keywords', content: config.keywork },
      ],
      link: [
        { rel: 'icon', type: 'image/x-icon', href: base+config.fanicon.url },
      ],
      bodyAttrs:{
        class: 'container mx-auto bg-white dark:bg-gray-900'
      }
    })
  </script>
  
