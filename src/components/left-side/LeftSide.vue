<script lang="ts" setup>
import SelectedItems from './SelectedItems.vue';
import { ref } from 'vue';
import { IItem } from '../shared/item.type.ts';
import { leftSideMockData } from './mock-data.ts';
import StoreItems from '../shared/StoreItems.vue';

const selected = ref(new Map<number, IItem>());
const limit = 6;

const onToggle = (item: IItem) => {
  if (selected.value.has(item.id)) {
    selected.value.delete(item.id);
  } else {
    if (selected.value.size === limit) return;

    selected.value.set(item.id, item);
  }
};
</script>
<template>
  <div class="left-side">
    <SelectedItems
      class="left-side-selected"
      :limit="limit"
      :items="selected"
    />
    <StoreItems :items="leftSideMockData" @toggle="onToggle" />
  </div>
</template>
<style>
.left-side {
  padding: 20px;
  display: flex;
  gap: 40px;
  flex-direction: column;
}
.left-side-selected {
  height: 250px;
}
</style>
