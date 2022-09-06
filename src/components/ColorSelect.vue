<script setup lang="ts">
import { computed, ref } from 'vue';
import BaseSelect from './BaseSelect.vue';
import BaseOption from './BaseOption.vue';

const colors = computed(() => [
  { value: '#000', label: 'black' },
  { value: '#F00', label: 'red' },
  { value: '#00F', label: 'blue' },
  { value: '#0F0', label: 'green' },
]);

const selected = ref();
</script>

<template>
  <BaseSelect :items="colors" v-model="selected">
    <template #default="item">
      <span class="preview" :style="{ backgroundColor: item.value }"></span>
      {{ item.label }}
    </template>
    <template #[`#000`]="item">
      {{ item.label }}
    </template>
  </BaseSelect>
</template>

<style scoped lang="scss">
.preview {
  width: 20px;
  height: 20px;
  display: inline-block;
}
</style>
