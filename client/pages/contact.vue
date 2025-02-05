<template>
  <div class="max-w-md mx-auto bg-white dark:bg-gray-800 rounded-lg shadow-lg overflow-hidden transition-transform transform hover:scale-105 relative">
    <div class="absolute inset-0 bg-gradient-to-r from-purple-600 to-indigo-600 opacity-30 rounded-lg"></div>
    <div class="flex items-center p-6 relative z-10 text-white">
      <div class="w-24 h-24 bg-white dark:bg-gray-700 rounded-full flex items-center justify-center shadow-lg">
        <i class="fas fa-user fa-3x text-gray-600"></i>
      </div>
      <div class="ml-4">
        <h2 class="text-4xl font-bold animate__animated animate__fadeIn text-black dark:text-white">Моника Будагова</h2>
        <p class="mt-1 text-lg animate__animated animate__fadeIn animate__delay-1s text-black dark:text-white">Веб-разработчик</p>
        <p class="mt-2 text-sm animate__animated animate__fadeIn animate__delay-2s text-black dark:text-white">Создаю современные веб-приложения с использованием передовых технологий.</p>
      </div>
    </div>

    <div class="p-6 border-t border-gray-200 dark:border-gray-600 relative z-10">
      <h3 class="text-lg font-semibold text-gray-800 dark:text-gray-200 animate__animated animate__fadeIn">Навыки:</h3>
      <div class="grid grid-cols-2 gap-4 mt-2">
        <button class="flex items-center p-2 bg-green-500 text-white rounded-lg shadow-lg hover:bg-green-600 transition duration-300 transform hover:scale-105 animate__animated animate__fadeIn animate__delay-3s">
          <i class="fab fa-vuejs fa-2x"></i>
          <span class="ml-2">Vue</span>
        </button>
        <button class="flex items-center p-2 bg-gray-800 text-white rounded-lg shadow-lg hover:bg-gray-700 transition duration-300 transform hover:scale-105 animate__animated animate__fadeIn animate__delay-3s">
          <i class="fab fa-nuxt fa-2x"></i>
          <span class="ml-2">Nuxt</span>
        </button>
        <button class="flex items-center p-2 bg-green-600 text-white rounded-lg shadow-lg hover:bg-green-700 transition duration-300 transform hover:scale-105 animate__animated animate__fadeIn animate__delay-3s">
          <i class="fab fa-node fa-2x"></i>
          <span class="ml-2">Node.js</span>
        </button>
        <button class="flex items-center p-2 bg-orange-500 text-white rounded-lg shadow-lg hover:bg-orange-600 transition duration-300 transform hover:scale-105 animate__animated animate__fadeIn animate__delay-3s">
          <i class="fas fa-database fa-2x"></i>
          <span class="ml-2">Strapi</span>
        </button>
        <button class="flex items-center p-2 bg-blue-500 text-white rounded-lg shadow-lg hover:bg-blue-600 transition duration-300 transform hover:scale-105 animate__animated animate__fadeIn animate__delay-3s">
          <i class="fab fa-tailwindcss fa-2x"></i>
          <span class="ml-2">Tailwind</span>
        </button>
        <button class="flex items-center p-2 bg-purple-500 text-white rounded-lg shadow-lg hover:bg-purple-600 transition duration-300 transform hover:scale-105 animate__animated animate__fadeIn animate__delay-3s">
          <i class="fas fa-paint-brush fa-2x"></i>
          <span class="ml-2">Flowbite</span>
        </button>
        <button class="flex items-center p-2 bg-orange-600 text-white rounded-lg shadow-lg hover:bg-orange-700 transition duration-300 transform hover:scale-105 animate__animated animate__fadeIn animate__delay-3s">
          <i class="fab fa-html5 fa-2x"></i>
          <span class="ml-2">HTML</span>
        </button>
        <button class="flex items-center p-2 bg-blue-600 text-white rounded-lg shadow-lg hover:bg-blue-700 transition duration-300 transform hover:scale-105 animate__animated animate__fadeIn animate__delay-3s">
          <i class="fab fa-css3-alt fa-2x"></i>
          <span class="ml-2">CSS</span>
        </button>
        <button class="flex items-center p-2 bg-yellow-500 text-white rounded-lg shadow-lg hover:bg-yellow-600 transition duration-300 transform hover:scale-105 animate__animated animate__fadeIn animate__delay-3s">
          <i class="fab fa-js fa-2x"></i>
          <span class="ml-2">JavaScript</span>
        </button>
      </div>

      <div class="p-6 border-t border-gray-200 dark:border-gray-600 relative z-10">
        <h3 class="text-lg font-semibold text-gray-800 dark:text-gray-200 animate__animated animate__fadeIn">Контакты:</h3>
        <div class="flex justify-center space-x-4 mt-2">
          <a href="https://t.me/immoniks" class="text-gray-600 hover:text-purple-500 transition-colors duration-200 transform hover:scale-110 animate__animated animate__fadeIn animate__delay-4s">
            <i class="fab fa-telegram fa-2x"></i>
          </a>
          <a href="mailto:budagova.monika5@yandex.ru" class="text-gray-600 hover:text-purple-500 transition-colors duration-200 transform hover:scale-110 animate__animated animate__fadeIn animate__delay-4s">
            <i class="fas fa-envelope fa-2x"></i>
          </a>
          <a href="tel:+79804757075" class="text-gray-600 hover:text-purple-500 transition-colors duration-200 transform hover:scale-110 animate__animated animate__fadeIn animate__delay-4s">
            <i class="fas fa-phone fa-2x"></i>
          </a>
        </div>
      </div>
    </div>

    <!-- Эффект искр -->
    <div class="absolute inset-0 pointer-events-none">
      <div class="sparkle"></div>
      <div class="sparkle"></div>
      <div class="sparkle"></div>
      <div class="sparkle"></div>
      <div class="sparkle"></div>
    </div>
  </div>
</template>

<script setup>
// Здесь можно добавить логику, если необходимо
</script>

<style scoped>
@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css');
@import url('https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css');

.sparkle {
  position: absolute;
  width: 10px;
  height: 10px;
  background: radial-gradient(circle, rgba(255, 255, 255, 0.8) 0%, rgba(255, 255, 255, 0) 100%);
  animation: sparkle 1.5s infinite;
  opacity: 0;
}

.sparkle:nth-child(1) {
  top: 20%;
  left: 10%;
  animation-delay: 0s;
}

.sparkle:nth-child(2) {
  top: 30%;
  left: 80%;
  animation-delay: 0.5s;
}

.sparkle:nth-child(3) {
  top: 60%;
  left: 30%;
  animation-delay: 1s;
}

.sparkle:nth-child(4) {
  top: 70%;
  left: 70%;
  animation-delay: 1.5s;
}

.sparkle:nth-child(5) {
  top: 40%;
  left: 50%;
  animation-delay: 2s;
}

@keyframes sparkle {
  0% {
    transform: scale(1);
    opacity: 0;
  }
  50% {
    transform: scale(1.5);
    opacity: 1;
  }
  100% {
    transform: scale(1);
    opacity: 0;
  }
}
</style>