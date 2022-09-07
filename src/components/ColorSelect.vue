<script setup lang="ts">
import { computed, ref } from 'vue';
import BaseSelect from './BaseSelect.vue';

const colors = computed(() => [
  { value: '#FFF', label: 'white' },
  { value: '#F00', label: 'red' },
  { value: '#0F0', label: 'green' },
  { value: '#00F', label: 'blue' },
]);

const selected = ref();
</script>

<template>
  <BaseSelect :items="colors" v-model="selected">
    <template #default="item">
      <span class="preview" :style="{ backgroundColor: item.value }" />
      {{ item.label }}
    </template>
    <template #[`#FFF`]="item">
      {{ item.label }}
    </template>
  </BaseSelect>
</template>

<style scoped lang="scss">
.preview {
  display: inline-block;
  width: 20px;
  height: 20px;
}
</style>
