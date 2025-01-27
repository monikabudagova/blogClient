<template>
    <header>
        <nav class="bg-white border-gray-200 dark:bg-gray-900 mb-4">
            <div class="navigHead max-w-screen-xl flex items-center justify-between mx-auto p-4">
                <NuxtLink to="/">
                    <a href="http://localhost:3000/" class="flex items-center space-x-3 rtl:space-x-reverse">
                        <img src="https://4ccc2241e457.vps.myjino.ru/uploads/free_icon_music_note_1816908_7084764faf.svg" class="h-10" alt="" />
                        <span class="self-center text-2xl font-semibold whitespace-nowrap dark:text-white">music</span>
                    </a>
                </NuxtLink>

                <div class="flex-grow flex justify-center md:justify-start">
                    <ul class="flex space-x-8">
                        <li>
                            <NuxtLink to="/" class="block py-2 px-5 text-gray-700 rounded hover:bg-gray-100 dark:text-white dark:hover:bg-gray-700 font-bold" :class="{ 'text-violet-500': isActive(''), 'dark:text-blue-700': isActive('') }">ГЛАВНАЯ</NuxtLink>
                        </li>
                        <li>
                            <NuxtLink to="/blog" class="block py-2 px-5 text-gray-700 rounded hover:bg-gray-100 dark:text-white dark:hover:bg-gray-700 font-bold" :class="{ 'text-violet-500': isActive('blog') || isActive('post') || isActive('category'), 'dark:text-blue-700': isActive('blog') || isActive('post') || isActive('category') }">СТАТЬИ</NuxtLink>
                        </li>
                        <li>
                            <NuxtLink to="/contact" class="block py-2 px-5 text-gray-700 rounded hover:bg-gray-100 dark:text-white dark:hover:bg-gray-700 font-bold" :class="{ 'text-violet-500': isActive('contact'), 'dark:text-blue-700': isActive('contact') }">КОНТАКТЫ</NuxtLink>
                        </li>
                    </ul>
                </div>

                <div class="flex items-center md:order-2 ml-auto space-x-4"> <!-- Сдвигаем вправо -->
                    <DarkMode class="mr-4" />
                    <div class="relative">
                        <div class="absolute inset-y-0 left-0 flex items-center pl-3 pointer-events-none">
                            <svg class="w-4 h-4 text-gray-500 dark:text-gray-400" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 20 20">
                                <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m19 19-4-4m0-7A7 7 0 1 1 1 8a7 7 0 0 1 14 0Z" />
                            </svg>
                        </div>
                        <input v-model="search.searchQuery" @focus="goToSearch" type="text" id="search-navbar" class="block w-64 p-2 pl-10 text-sm text-gray-900 border border-gray-300 rounded-lg bg-gray-50 focus:ring-blue-500 focus:border-blue-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="Поиск...">
                    </div>
                </div>
            </div>
        </nav>
    </header>
</template>

<script setup>
import { useSearchStore } from '~/stores/search'

const search = useSearchStore()
const route = useRoute()
const isActive = (path) => route.path.split('/')[1] === path

const router = useRouter()
function goToSearch() {
    router.push({ path: '/search' })

}

useHead({
    script: [
        {
            src: 'https://cdn.jsdelivr.net/npm/flowbite@2.5.2/dist/flowbite.min.js',
            async: true,
            defer: true
        }
    ]
})
</script>
<style scoped>

@media (max-width: 768px) {
    .navigHead {
        flex-direction: column; /* Изменяем направление на колонку для мобильных устройств */
        align-items: flex-start; /* Выравниваем элементы по левому краю */
    }

    .flex-grow {
        justify-content: center; /* Центрируем элементы навигации на мобильных устройствах */
        margin-bottom: 10px; /* Добавляем отступ снизу для разделения с поиском */
    }

    .space-x-8 {
        flex-direction: column; /* Изменяем направление на колонку для мобильных устройств */
        align-items: center; /* Центрируем элементы навигации */
        margin: 0; /* Убираем отступы между элементами */
    }

    .space-x-8 li {
        margin-bottom: 10px; /* Добавляем отступ между элементами навигации */
    }

    .relative {
        width: 100%; /* Поле поиска занимает всю ширину */
    }

    .block {
        width: 100%; /* Устанавливаем ширину для ссылок */
    }
}

@media (min-width: 769px) {
    .navigHead {
        flex-direction: row; /* Возвращаем направление на строку для больших экранов */
    }

    .space-x-8 {
        flex-direction: row; /* Устанавливаем горизонтальное направление для навигации */
    }

    .space-x-8 li {
        margin-bottom: 0; /* Убираем отступы между элементами навигации на больших экранах */
    }
}

</style>