<script setup lang="ts">
import { stringifyStyle } from '@vue/shared';
import { computed, ref } from 'vue';

const props = defineProps<{
  items: { value: string; label: string }[];
  modelValue: string;
}>();

defineEmits(['update:model-value']);

const isOpen = ref(false);

const selectedOptionsLabel = computed(() => {
  return (
    props.items.find(({ value }) => value === props.modelValue)?.label ||
    'Select'
  );
});
</script>

<template>
  <div class="select">
    <button aria-haspopup="true" aria-controls="list" @click="isOpen = !isOpen">
      {{ selectedOptionsLabel }}
    </button>
    <div
      v-if="isOpen"
      id="list"
      role="listbox"
      :aria-activedescendant="modelValue"
    >
      <div
        v-for="item in items"
        :key="item.value"
        :value="item.value"
        role="option"
        @click="$emit('update:model-value', item.value)"
      >
        <slot :name="item.value" v-bind="item">
          <slot v-bind="item">
            {{ item.label }}
          </slot>
        </slot>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
select {
  width: 300px;
  padding: 12px;
}
</style>
