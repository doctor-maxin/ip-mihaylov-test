<script lang="ts" setup>
import { IItem } from '../shared/item.type.ts';
import Item from '../shared/item.vue';

defineProps<{
  items: Map<number, IItem>;
  limit: number;
}>();
</script>
<template>
  <div class="selected-items container">
    <div class="store">
      <Item v-for="[id, item] of items" :key="id" :item="item" />
    </div>
    <span>selected: {{ items.size }} / {{ limit }}</span>
  </div>
</template>
<style scoped>
.selected-items {
  max-width: 300px;
}
.store {
  margin-bottom: 30px;
}
</style>
