<template>
  <div class="couple-view" id="couple">
    <brides-name />
    <bagian-surah />
  </div>
</template>

<script>
import BridesName from '../components/BridesName.vue'
import BagianSurah from '../components/BagianSurah.vue'
export default {
  components: { 
      BridesName,
      BagianSurah,
  },

}
</script>

<style>
  .couple-view {
    display: none;
  }
</style>