<template>
  <div class="event-view" id="event">
    <jadwal-event />
    <journey-timeline />
  </div>
</template>

<script>
import JadwalEvent from '../components/JadwalEvent.vue'
import JourneyTimeline from '../components/JourneyTimeline.vue'

export default {
  components: { 
    JadwalEvent,
    JourneyTimeline,
  },

}
</script>

<style>
  .event-view {
    display: none;
  }
</style>