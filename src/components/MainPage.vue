<script setup lang="ts">
import FmHeader from './FmHeader.vue';
import FmContent from './FmContent.vue';
</script>

<template>
  <fm-header />
  <fm-content />
  <div class="back">
    <img src="../assets/background.png" alt="background-image">
  </div>
</template>

<style scoped>
.back {
  position: absolute;
  object-fit: cover;
  object-position: center;
  z-index: -1;
  overflow: auto;
  width: 100%;
}
@media (max-width: 960px) {
  .back {
    max-height: 585px;
  }
}
@media (min-width: 961px) {
  .back {
    height: 100%;
    width: 100%;
  }
}
</style>
