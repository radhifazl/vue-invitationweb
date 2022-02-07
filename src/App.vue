<template>
  <cover-page />
  <home/>
  <couples />
  <event />
  <gallery />
  <wishes />
</template>

<script>
import CoverPage from './components/CoverPage.vue'
import Couples from './views/Couples.vue'
import Event from './views/Event.vue'
import Gallery from './views/Gallery.vue'
import Home from './views/Home.vue'
import Wishes from './views/Wishes.vue'

export default {
  name: 'App',
  components: {
    CoverPage,
    Home,
    Couples,
    Event,
    Gallery,
    Wishes,
  }
}
</script>

<style>
  /* === FONTS === */
  @import url('https://fonts.googleapis.com/css2?family=Cabin:wght@400;600&family=Montserrat:wght@200;400;600;700&family=Roboto:wght@100;300;400;500;700&family=Rochester&family=Sarabun&display=swap');
  /* === Variables === */
  :root {
      /* === Font === */
      --first-font: 'Rochester', sans-serif;
      --second-font: 'Montserrat', sans-serif;
      --third-font: 'Roboto', sans-serif;
      --cabin: 'Cabin', sans-serif;
      --footer-font: 'Sarabun', sans-serif;

      /* === Colors === */
      --primary-color: #89492B;
      --secondary-color: #B3541E;
      --tertiary-color: #543423;

      /* ===  fc / Font Colors === */
      --first-fc: #FDD08C;
      --second-fc: #67481A;
      --black-fc: #000000;
      --white-fc: #ffffff;
      --msg-fc: #292B3A;
  }

  * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      color: var(--white-fc);
  }

  html, body {
      scroll-behavior: smooth;
  }

  a {
      text-decoration: none;
  }

  li {
    list-style: none;
  }

  img {
      user-select: none;
  }

  /* === Usable Class === */
  .font-title {
      font-family: var(--first-font);
  }

  .font-sub {
      font-family: var(--second-font);
  }

  .wood-bg {
    background: url("./assets/images/WoodBG2.jpeg");
    background-size: cover;
    background-position: center;
    position: relative;
  }

  .wood-bg::after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: #89492bbd;
  }

  .wrapper-z-idx {
    position: absolute;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    z-index: 1000;
  }
</style>
