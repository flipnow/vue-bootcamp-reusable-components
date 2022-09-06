<script setup lang="ts">
defineProps<{
  items: { value: string; label: string }[];
}>()
</script>

<template>
  <select>
    <slot />
  </select>
</template>

<style scoped lang="scss">

</style>