<script setup lang="ts">
import BaseSelect from './components/BaseSelect.vue';
import { computed } from 'vue';
import CurrencySelect from './components/CurrencySelect.vue';
import ColorSelect from './components/ColorSelect.vue';

  const items = computed(() => [
    { value: 'value 1', label: 'option 1'},
    { value: 'value 2', label: 'option 2'},
    { value: 'value 3', label: 'option 3'},
  ])
</script>

<template>
  <div class="content">
    <CurrencySelect />
    <ColorSelect />
  </div>
</template>

<style scoped lang="scss">
  .content {
    display: flex;
    gap: 16px;
  }
</style>
