<script setup lang="ts">
import FmHeader from './FmHeader.vue';
import FmContent from './FmContent.vue';
</script>

<template>
  <fm-header />
  <fm-content />
  <img src="../assets/background.png" alt="background-image">
</template>

<style scoped>
img {
  position: absolute;
  height: 100%;
  width: 100%;
  object-fit: cover;
  object-position: center;
  z-index: -1;
}
</style>
