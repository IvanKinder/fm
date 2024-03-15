<script setup lang="ts">
import FmHeader from './FmHeader.vue';
import FmContent from './FmContent.vue';
import { ref } from 'vue';

const overAll = ref(false);
const setOver = () => {
  overAll.value = !overAll.value;
}

</script>

<template>
  <fm-header />
  <fm-content :setOver="setOver" />
  <div class="back" :class="{'over': overAll}">
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
  max-height: 712px;
}
@media (max-width: 320px) {
  .back {
    max-height: 600px;
  }
}
@media (min-width: 961px) {
  .back {
    height: 100%;
    width: 100%;
  }
}
.over {
  z-index: 1;
}
</style>
