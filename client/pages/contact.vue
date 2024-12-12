<template>
    <h2>Контакты</h2>
    <main>
        <h1>monika</h1>
        <div class="gallery">
        <img src="https://via.placeholder.com/150" alt="Image 1">
        <img src="https://via.placeholder.com/150" alt="Image 2">
        <img src="https://via.placeholder.com/150" alt="Image 3">
        <img src="https://via.placeholder.com/150" alt="Image 4">
        <img src="https://via.placeholder.com/150" alt="Image 5">
    </div>
</main>

</template>

<style scoped>
.gallery {
    display: flex;
    justify-content: center;
    align-items: center;
    display: flex;
    gap: 20px;
}

.gallery img {
    width: 150px;
    height: 150px;
    transition: transform 0.3s ease;
    border-radius: 10px;
}

.gallery img:hover {
    transform: scale(1.2) translateY(-10px);
}

body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #f0f0f0;
    margin: 0;
}

main{
    color: #000000;
    background-color: #5271FF;
}
h2{
    display: flex;
    justify-content: center;
}

main, h2{
    color: #000000;
    background-color: #95B1EE;
} 
</style>