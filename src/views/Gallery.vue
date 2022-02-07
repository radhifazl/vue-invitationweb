<template>
  <div class="gallery-view" id="gallery">
    <gallery-photo />
  </div>
</template>

<script>
import GalleryPhoto from '../components/GalleryPhoto.vue'
export default {
  components: { GalleryPhoto },

}
</script>

<style>
  .gallery-view {
    display: none;
  }
</style>