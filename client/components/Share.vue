<template>
    <div class="absolute -left-20 top-2 ya-share2" data-curtain
        data-services="telegram,whatsapp"
        data-url="https://t.me/immoniks" 
        data-title="Посетите мой GitHub" 
        data-description="Здесь вы найдете мои проекты и репозитории." 
        data-image="https://wa.me/79804757075"></div>
</template>

<script setup>
import { onMounted } from 'vue';

// Загрузка скрипта Yandex Share
const loadShareScript = () => {
    if (!document.querySelector('script[src="https://yastatic.net/share2/share.js"]')) {
        const script = document.createElement('script');
        script.src = 'https://yastatic.net/share2/share.js';
        script.async = true;
        script.defer = true;
        document.head.appendChild(script);
    }
};

// Вызываем загрузку скрипта при монтировании компонента
onMounted(loadShareScript);
</script>

<style>
.ya-share2__list {
    display: flex !important;
    flex-flow: column !important;
}

.ya-share2__list:hover li {
    filter: grayscale(1);
}

.ya-share2__list li:hover {
    filter: grayscale(0);
}
</style>