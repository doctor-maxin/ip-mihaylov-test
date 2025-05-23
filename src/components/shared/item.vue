<script setup lang="ts">
import type { IItem } from './item.type.ts';

const { item } = defineProps<{
  item: IItem | null;
}>();
</script>

<template>
  <div class="container store-item">{{ item ? item.name : 'N\\S' }}</div>
</template>

<style scoped>
.store-item {
  display: block;
  cursor: pointer;
  aspect-ratio: 1 / 1;
  max-width: 100px;
}
</style>
