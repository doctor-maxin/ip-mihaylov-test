<script setup lang="ts">
import LeftSide from './components/left-side/LeftSide.vue';
import RightSide from './components/right-side/RightSide.vue';
</script>
<template>
  <div class="content">
    <LeftSide />
    <RightSide />
  </div>
</template>

<style scoped>
.content {
  display: grid;
  grid-template-columns: 1fr;
  gap: 100px;
  min-height: 100vh;
}
@media screen and (min-width: 1024px) {
  .content {
    grid-template-columns: 1fr 1fr;
  }
}
</style>
