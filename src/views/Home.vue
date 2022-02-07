<template>
  <div class="home-view" id="home">
    <first-section />
    <date-countdown />
  </div>
</template>

<script>
import FirstSection from '../components/FirstSection.vue'
import DateCountdown from '../components/DateCountdown.vue'

export default {
    components: {
        FirstSection,
        DateCountdown,
    }
}
</script>

<style>
  .home-view {
    display: none;
  }
</style>