<template>
  <div class="container mx-auto px-4 py-10">
    <div class="shadow-lg rounded-lg overflow-hidden">
      <div class="bg-gradient-to-r from-indigo-600 to-purple-600 p-8">
        <h1 class="text-5xl font-bold text-center text-black dark:text-white">Моника, 16 лет</h1>
        <p class="text-center text-lg mt-2 text-black dark:text-white">Веб-разработчик</p>
      </div>
      <div class="p-8">
        <h2 class="text-3xl font-semibold mb-4 text-black dark:text-white">О себе</h2>
        <p class="text-black dark:text-white mb-6 ">
          Я веб-разработчик, недавно окончила курс по веб-разработке. Увлекаюсь созданием интерактивных веб-приложений и постоянно изучаю новые технологии. Моя цель — создавать удобные и функциональные сайты, которые будут приносить пользу пользователям.
        </p>

        <h2 class="text-3xl font-semibold mb-4 text-black dark:text-white">Контактная информация</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-6">
          <a href="https://t.me/immoniks" class="flex items-center justify-center bg-purple-600 text-white font-semibold py-3 rounded-lg shadow-md hover:bg-purple-700 transition duration-200 transform hover:scale-105">
            <img src="https://img.icons8.com/ios-filled/24/ffffff/telegram-app.png" alt="Telegram" class="mr-2" />
            <span class="text-black dark:text-white">Телеграм</span>
          </a>
          <a href="tel:+79804757075" class="flex items-center justify-center bg-purple-600 text-white font-semibold py-3 rounded-lg shadow-md hover:bg-purple-700 transition duration-200 transform hover:scale-105">
            <img src="https://img.icons8.com/ios-filled/24/ffffff/phone.png" alt="Phone" class="mr-2" />
            <span class="text-black dark:text-white">Номер</span>
          </a>
          <a href="mailto:budagova.monika5@yandex.ru" class="flex items-center justify-center bg-purple-600 text-white font-semibold py-3 rounded-lg shadow-md hover:bg-purple-700 transition duration-200 transform hover:scale-105">
            <img src="https://img.icons8.com/ios-filled/24/ffffff/email.png" alt="Email" class="mr-2" />
            <span class="text-black dark:text-white">Email</span>
          </a>
          <a href="https://github.com/your-github-username" class="flex items-center justify-center bg-purple-600 text-white font-semibold py-3 rounded-lg shadow-md hover:bg-purple-700 transition duration-200 transform hover:scale-105">
            <img src="https://img.icons8.com/ios-filled/24/ffffff/github.png" alt="GitHub" class="mr-2" />
            <span class="text-black dark:text-white">GitHub</span>
          </a>
        </div>

        <h2 class="text-3xl font-semibold mb-4 text-black dark:text-white">Мои навыки</h2>
        <div class="grid grid-cols-2 gap-4">
          <div class="p-4 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-200">
            <p class="ont-semibold text-black dark:text-white">Node.js</p>
          </div>
          <div class="p-4 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-200">
            <p class="font-semibold text-black dark:text-white">Strapi</p>
          </div>
          <div class="p-4 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-200">
            <p class="font-semibold text-black dark:text-white">Vue.js</p>
          </div>
          <div class="p-4 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-200">
            <p class="font-semibold text-black dark:text-white">Nuxt.js</p>
          </div>
          <div class="p-4 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-200">
            <p class="font-semibold text-black dark:text-white">Pinia</p>
          </div>
          <div class="p-4 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-200">
            <p class="font-semibold text-black dark:text-white">TailwindCSS</p>
          </div>
          <div class="p-4 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-200">
            <p class="font-semibold text-black dark:text-white">Flowbite</p>
          </div>
          <div class="p-4 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-200">
            <p class="font-semibold text-black dark:text-white">Postman</p>
          </div>
          <div class="p-4 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-200">
            <p class="font-semibold text-black dark:text-white">Figma</p>
          </div>
          <div class="p-4 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-200">
            <p class="font-semibold text-black dark:text-white">Nginx</p>
          </div>
          <div class="p-4 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-200">
            <p class="font-semibold text-black dark:text-white">PM2</p>
          </div>
          <div class="p-4 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-200">
            <p class="font-semibold dark:text-white">MySQL</p>
          </div>
          <div class="p-4 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-200">
            <p class="font-semibold text-black dark:text-white">npm и yarn</p>
          </div>
          <div class="p-4 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-200">
            <p class="font-semibold text-black dark:text-white">Git</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
  // Здесь можно добавить логику, если это необходимо
</script>

<style scoped>
  /* Добавим немного стилей для улучшения дизайна */
  .container {
    max-width: 800px; /* Ограничим ширину контейнера */
  }

  h1, h2 {
    text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5); /* Добавим тень к заголовкам */
  }

  .bg-gradient-to-r {
    background-size: 200% 200%; /* Увеличим размер градиента для анимации */
    animation: gradient 5s ease infinite; /* Добавим анимацию градиента */
  }

  @keyframes gradient {
    0% {
      background-position: 0% 50%;
    }
    50% {
      background-position: 100% 50%;
    }
    100% {
      background-position: 0% 50%;
    }
  }
</style>