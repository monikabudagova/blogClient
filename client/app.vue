<template>
  <NuxtLoadingIndicator throttle="0" />
  <Navbar />
  <NuxtPage />
  <Up />
  <Footer />
</template>

<script setup>
const base = 'https://4ccc2241e457.vps.myjino.ru';
const isDarkMode = ref('');
const isDark = ref(false);
const config = ref({});

const fetchConfig = async () => {
  try {
    const api = await $fetch(`${base}/api/config?populate=*`);
    config.value = api.data;

    // Установка метаданных после получения конфигурации
    useHead({
      title: config.value.title || 'Default Title',
      meta: [
        { name: 'description', content: config.value.desc || 'Default description' },
        { name: 'keywords', content: config.value.keywords || 'Default keywords' },
      ],
      link: [
        {
          rel: 'icon',
          type: 'image/x-icon',
          href: config.value.fanicon ? base + config.value.fanicon[0].url : ''
        },
        {
          rel: 'stylesheet',
          href: 'https://cdn.jsdelivr.net/npm/flowbite@2.5.2/dist/flowbite.min.css',
        },
      ],
      htmlAttrs: {
        class: isDarkMode.value
      },
      bodyAttrs: {
        class: 'container mx-auto bg-white dark:bg-gray-900'
      },
      head: {
        script: [
          {
            src: 'https://yastatic.net/share2/share.js',
            async: true,
            defer: true
          },
          {
            src: 'https://cdn.jsdelivr.net/npm/flowbite@2.5.2/dist/flowbite.min.js',
            async: true,
            defer: true
          }
        ]
      }
    });

  } catch (error) {
    console.error('Error fetching config:', error);
  }
};

onMounted(() => {
  fetchConfig();
  if (localStorage.getItem('color-theme') === 'dark') {
    isDark.value = true;
    isDarkMode.value = 'dark';
  } else {
    isDark.value = false;
    isDarkMode.value = '';
  }
});
</script>