<script setup lang="ts">
import { computed } from 'vue';
import CurrencySelect from './components/CurrencySelect.vue';
import ColorSelect from './components/ColorSelect.vue';

const items = computed(() => [
  { value: 'value 1', label: 'option 1' },
  { value: 'value 2', label: 'option 2' },
  { value: 'value 3', label: 'option 3' },
]);
</script>

<template>
  <div class="content">
    <CurrencySelect />
    <ColorSelect />
  </div>
</template>

<style scoped>
.content {
  display: flex;
  gap: 16px;
}
</style>
