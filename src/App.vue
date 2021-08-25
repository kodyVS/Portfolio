<template>
  <router-view />
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
body {
  font-size: 1.6rem;
  background-image: linear-gradient(
      270deg,
      rgba(255, 255, 255, 0.6) 0,
      white 100%
    ),
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
