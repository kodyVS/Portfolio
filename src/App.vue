<template>
  <!-- CURRENTLY IN ANIMATION BRANCH -->
  <div class="div">
    <router-view class="router-view" />
    <img class="gear-image" :src="require('./assets/img/test-gearv1.0.1.png')" />
    <img class="gear-image2" :src="require('./assets/img/test-gearv1.0.1.png')" />
  </div>
</template>

<style>
*,
*:before,
*:after {
  padding: 0;
  margin: 0;
}
html {
  font-size: 62.5%;
  box-sizing: border-box;
}
.gear-image {
  z-index: -1;
  opacity: 0.2;
  height: 700px;
  position: fixed;
  top: 0;
  left: 0;
  animation: turn 100s infinite linear;
  animation-direction: forwards;
}
.gear-image2 {
  z-index: -1;
  opacity: 0.2;
  height: 700px;
  position: fixed;
  top: 550px;
  left: 365px;
  animation: turn2 100s infinite linear;
  animation-direction: forwards;
}
@keyframes turn {
  0% {
    transform: rotate(0);
  }
  50% {
  }
  100% {
    transform: rotate(360deg);
  }
}
@keyframes turn2 {
  0% {
    transform: rotate(325deg);
  }
  50% {
  }
  100% {
    transform: rotate(-30deg);
  }
}
body {
  font-size: 1.6rem;
  background-image: linear-gradient(270deg, rgba(255, 255, 255, 0.6) 0, white 100%),
    url("./assets/img/background-gears.jpg");
  height: 95vh;
  background-size: 200%;
  background-position: 40% 50%;
  font-family: Geomanist, Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #131313;
}
.v-lazy-image {
  filter: blur(5px);
  transition: filter 0.2s;
}

.v-lazy-image-loaded {
  filter: blur(0);
}
@media only screen and (max-width: 800px) {
  html {
    font-size: 55%;
    box-sizing: border-box;
  }
  body {
    background-size: cover;
  }
}
</style>
