<script lang="ts" setup>
import type { IItem } from './item.type';
import Item from './item.vue';

defineProps<{
  items: IItem[];
}>();

const emit = defineEmits<{
  (e: 'toggle', payload: IItem): void;
}>();

const onToggle = (item: IItem) => {
  emit('toggle', item);
};
</script>
<template>
  <div class="container store">
    <template v-for="item of items" :key="item.id">
      <Item :item="item" @click="onToggle(item)" />
    </template>
  </div>
</template>
