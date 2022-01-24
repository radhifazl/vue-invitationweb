<template>
  <first-section />
  <date-countdown />
  <brides-name />
  <bagian-surah />
  <jadwal-event />
  <journey-timeline />
</template>

<script>
import FirstSection from './components/FirstSection.vue'
import DateCountdown from './components/DateCountdown.vue'
import BridesName from './components/BridesName.vue'
import JadwalEvent from './components/JadwalEvent.vue'
import BagianSurah from './components/BagianSurah..vue'
import JourneyTimeline from './components/JourneyTimeline.vue'

export default {
  name: 'App',
  components: {
    FirstSection,
    DateCountdown,
    BridesName,
    JadwalEvent,
    BagianSurah,
    JourneyTimeline,
  }
}
</script>

<style>
  /* === FONTS === */
  @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@200;400;600;700&family=Rochester&display=swap');

  /* === Variables === */
  :root {
      /* === Font === */
      --first-font: 'Rochester', cursive;
      --second-font: 'Montserrat', sans-serif;

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
