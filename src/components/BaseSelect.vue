<script setup lang="ts">
import { computed, ref } from 'vue';
import BaseOption from './BaseOption.vue';

const props = defineProps<{
  items: { value: string; label: string }[];
  modelValue?: string;
}>();

defineEmits(['update:model-value']);

const selectedOption = computed(() => {
  return (
    props.items.find(({ value }) => props.modelValue === value)?.label ||
    'select'
  );
});

const isOpen = ref(false);
</script>

<template>
  <div class="select">
    <button
      id="button"
      aria-haspopup="listbox"
      :aria-expanded="isOpen"
      @click="isOpen = !isOpen"
    >
      {{ selectedOption }}
    </button>
    <div
      v-if="isOpen"
      id="list"
      role="listbox"
      :aria-activedescendant="modelValue"
    >
      <BaseOption
        v-for="item in items"
        :key="item.value"
        :id="item.value"
        @click="$emit('update:model-value', item.value)"
      >
        <slot :name="item.value" v-bind="item">
          <slot v-bind="item">
            {{ item.label }}
          </slot>
        </slot>
      </BaseOption>
    </div>
  </div>
</template>

<style scoped lang="scss">
.select {
  position: relative;
}

button {
  width: 200px;
  padding: 12px;
}

#list {
  position: absolute;
  top: 100%;
  padding-left: 12px;
}
</style>
