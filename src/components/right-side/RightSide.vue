<script lang="ts" setup>
import type { IItem } from '../shared/item.type';
import Item from '../shared/item.vue';
import StoreItems from '../shared/StoreItems.vue';
import { rightSideMockData } from './mock-data';
import { ref } from 'vue';

const selected = ref<IItem | null>(null);

const onToggle = (item: IItem) => {
  if (selected.value?.id === item.id) {
    selected.value = null;
  } else {
    selected.value = item;
  }
};
</script>
<template>
  <div class="right-side">
    <Item class="right-side-selected" :item="selected" />
    <StoreItems :items="rightSideMockData" @toggle="onToggle" />
  </div>
</template>
<style>
.right-side {
  padding: 20px;
  display: flex;
  align-items: end;
  gap: 40px;
  flex-direction: column;
}
.right-side .container {
  justify-content: end;
}
.right-side .right-side-selected {
  height: 250px;
  width: 300px;
  max-width: unset;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
