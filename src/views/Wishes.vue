<template>
  <div class="wishes-view" id="wishes">
    <buku-tamu />
    <footer-section />
  </div>
</template>

<script>
import BukuTamu from '../components/BukuTamu.vue'
import FooterSection from '../components/FooterSection.vue'
export default {
  components: { BukuTamu, FooterSection },

}
</script>

<style>
  .wishes-view {
    display: none;
  }
</style>