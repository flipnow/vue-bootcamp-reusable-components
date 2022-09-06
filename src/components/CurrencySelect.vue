<script setup lang="ts">
import { computed, ref } from 'vue';
import BaseSelect from './BaseSelect.vue';
import BaseOption from './BaseOption.vue';

const selected = ref();

const currencies = computed(() => [
  { value: 'EUR', label: 'euro' },
  { value: 'PLN', label: 'zloty' },
  { value: 'USD', label: 'dollar' },
]);
</script>

<template>
  <BaseSelect :items="currencies" v-model="selected">
    <template #default="item"> {{ item.label }} - {{ item.value }} </template>
  </BaseSelect>
</template>

<style scoped lang="scss"></style>
