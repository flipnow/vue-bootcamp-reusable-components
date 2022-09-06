<script setup lang="ts">
import BaseSelect from './components/BaseSelect.vue';
import { computed } from 'vue';

  const items = computed(() => [
    { value: 'value 1', label: 'option 1'},
    { value: 'value 2', label: 'option 2'},
    { value: 'value 3', label: 'option 3'},
  ])
</script>

<template>
  <div>
    <BaseSelect :items="items" />
  </div>
</template>

<style scoped>
</style>
