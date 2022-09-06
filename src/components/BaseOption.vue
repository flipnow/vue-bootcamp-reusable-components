<script setup lang="ts"></script>

<template>
  <div role="option"><slot /></div>
</template>

<style scoped lang="scss">
div {
  width: 100%;
  cursor: pointer;

  &:hover {
    color: lightblue;
  }
}
</style>
