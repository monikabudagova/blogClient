<template>
    <main>
        <div class="business-card" ontouchstart="this.classList.toggle('hover');">
  <div class="flipper">
    <div class="front">
      <div class="name">
          <span class="first">Будагова</span> 
          <span class="last">Моника</span>
          <span class="title">Web Developer</span>
        </div>
    </div>
    <div class="back">
      <div class="container-sm">
        <figure class="logo-white"></figure>
      </div>
      <div class="container-lg">
        <ul class="social fa-ul">
          <li><i class="fa fa-li fa-envelope"></i><a href="mailto:budagova.monika5@yandex.ru">budagova@yandex.ru</a></li>
          <li><i class="fa fa-li fa-phone"></i><a href="tel:+79804757075">+7 (980)-475-70 75</a></li>
          <li><i class="fa fa-li fa-github"></i><a href="https://github.com/monikabudagova">GitHub</a></li>
        </ul>
      </div>
    </div>
  </div>
</div>

<link href="//maxcdn.bootstrapcdn.com/font-awesome/4.1.0/css/font-awesome.min.css" rel="stylesheet">


<div class="bouncing-blobs-container">
  <div class="bouncing-blobs-glass"></div>
  <div class="bouncing-blobs">
    <div class="bouncing-blob bouncing-blob--blue"></div>
    <div class="bouncing-blob bouncing-blob--blue"></div>
    <div class="bouncing-blob bouncing-blob--blue"></div>
    <div class="bouncing-blob bouncing-blob--white"></div>
    <div class="bouncing-blob bouncing-blob--purple"></div>
    <div class="bouncing-blob bouncing-blob--purple"></div>
    <div class="bouncing-blob bouncing-blob--pink"></div>
  </div>
</div>
<div class="hero  text-black  dark:text-white">
  <h2>КОНТАКТЫ</h2>

</div>
</main>

</template>
<script setup>


</script>

<style scoped>
:root {
  font-family: Inter, system-ui, Avenir, Helvetica, Arial, sans-serif;
  line-height: 1.5;
  font-weight: 400;

  color: black;
  background-color: whitesmoke;

  font-synthesis: none;
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

body {
  margin: 0;
  display: flex;
  place-items: center;
  min-width: 320px;
  min-height: 100vh;
}

.bouncing-blob {
  width: 32vw;
  aspect-ratio: 1;
  border-radius: 50%;
  will-change: transform;
  position: absolute;
  z-index: 1;
  top: 0;
  left: 0;
  transform-origin: left top;
}
/* 
.bouncing-blob--blue {
  background: #4783c7;
}

.bouncing-blob--white {
  background: #ffffff;
  z-index: 2;
  width: 15vw;
}

.bouncing-blob--purple {
  background: #8c8ff1;
}

.bouncing-blob--pink {
  background: #e289cd50;
} */

.bouncing-blobs-container {
  position: fixed;
  z-index: -1;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.bouncing-blobs-glass {
  position: absolute;
  z-index: 2;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  backdrop-filter: blur(140px);
  -webkit-backdrop-filter: blur(140px);
  pointer-events: none;
}

.bouncing-blobs {
  position: absolute;
  z-index: 1;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.hero {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
}

.hero h2 {
  font-size: 70px;
  max-width: 800px;
  line-height: 1;
  text-align: center;
  font-weight: bold;
  text-transform: capitalize;
  margin-bottom: 20px;

}

.hero p {
  font-size: 24px;
  max-width: 500px;
  text-align: center;

}

@media (max-width: 1200px) {
  .bouncing-blobs-glass {
    backdrop-filter: blur(120px);
    -webkit-backdrop-filter: blur(120px);
  }
}

@media (max-width: 500px) {
  .bouncing-blob {
    width: 60vw;
  }
  .bouncing-blob--white {
    width: 30vw;
  }
  .bouncing-blobs-glass {
    backdrop-filter: blur(90px);
    -webkit-backdrop-filter: blur(90px);
  }

  .hero h2 {
    font-size: 32px;
  }

  .hero p {
    font-size: 16px;
    padding: 0 20px;
  }
}

.tutorial-link a {
  display: flex;
  justify-content: center;
  align-items: center;
  color: black;
  font-size: 20px;
  text-decoration: none;
  font-weight: 600;
  gap: 0 5px;
  border: 2px solid;
  border-radius: 5px;
  padding: 4px 10px;
}

.tutorial-link svg {
  width: 30px;
}

@media(max-width: 500px) {
  .tutorial-link a {
    font-size: 14px;
    padding: 2px 4px;
  }
  .tutorial-link svg {
    width: 15px;
  }
}
body {
  background-image: url(https://subtlepatterns.com/patterns/gplaypattern.png);
  background-position: center center;
  font-family: 'Open Sans', sans-serif;
}

div.business-card {
  height: 427px;
  width: 320px;
  margin-left: -160px; /* $width/-2 */
  margin-top: -213.5px; /* $height/-2 */
  
  position: absolute;
  top: 50%;
  left: 50%;
  
  perspective: 1000;
}

div.business-card:hover .flipper,
div.business-card.hover .flipper {
  transform: rotateY(180deg) rotateZ(90deg);
}

div.flipper {
  transition: 0.6s;
  transform-style: preserve-3d;

  position: relative;
  transform-origin: center 160px; /* $width/2 */
}

div.front,
div.back {
  backface-visibility: hidden;

  position: absolute;
  top: 0;
  left: 0;
  height: 427px; /* $height */
  width: 320px; /* $width */
 
  box-shadow: 0 0 50px rgba(0, 0, 0, 0.75);
}

div.front {
  background-color: white;
  z-index: 0;
}

div.front:before,
div.front:after {
  display: block;
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  border-width: 160px; /* $width/2 */
  border-style: solid;
  border-color: transparent;
}

div.front:before {
  border-top-color: #5271FF; /* $light-blue */
  border-left-color: #5271FF; /* $light-blue */
  z-index: 2;
}

div.front:after {
  border-top-color: #e978ff; /* $dark-blue */
  border-right-color: #e978ff; /* $dark-blue */
}

div.front div.name {
  position: absolute;
  bottom: 43.5px; /* ($height - $width - 90)/2 */
  left: 85px; /* ($width - 150px) / 2 */
}

div.front div.name span {
  display: block;
  font-size: 40px;
  line-height: 45px;
}

div.front div.name span.first {
  color: #5271FF; /* $dark-blue */
}

div.front div.name span.last {
  color: #e978ff; /* $light-blue */
}

div.front div.name span.title {
  font-size: 20px;
  line-height: 20px;
}

div.back {
  background-color: #d189f8; /* $dark-blue */
  color: white;
  width: 427px; /* $height */
  height: 320px; /* $width */
  box-sizing: border-box;
  transform: rotateY(180deg) rotateZ(90deg);
}

div.back div.container-sm {
  float: left;
  width: 40%;
  height: 100%;
  position: relative;
}

div.back div.container-lg {
  float: left;
  width: 60%;
  margin-top: 2rem;
}

div.back figure.logo-white {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 120px;
  height: 120px;
  display: block;
  margin: -60px -60px;
}

div.back figure.logo-white:before,
div.back figure.logo-white:after {
  display: block;
  content: '';
  position: absolute;
  border-style: solid;
  border-color: transparent;
}

div.back figure.logo-white:before {
  top: 0;
  left: 0;
  border-width: 60px;
  border-top-color: white;
  border-left-color: white;
  z-index: 2;
}

div.back figure.logo-white:after {
  bottom: 0;
  right: 0;
  border-width: 56px;
  border-right-color: white;
}

div.back a {
  color: white;
  text-decoration: none;
  display: block;
}

div.back a:hover {
  text-decoration: underline;
}

div.back ul.social {
  font-size: 1.25rem;
}

div.back ul.social li {
  margin-top: 1rem;
}

div.back ul.social li:first-child {
  margin-top: 2rem;
}
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

}



</style>