<script lang="ts" setup>
import type { TaskFilter } from "../types";

const props = defineProps<{
  currentFilter: TaskFilter;
  filter: TaskFilter;
}>();

const emits = defineEmits<{
  setFilter: [filter: TaskFilter];
}>();
</script>

<template>
  <button
    class="secondary"
    @click="emits('setFilter', props.filter)"
    :class="{
      contrast: props.currentFilter === props.filter,
    }"
  >
    {{ props.filter }}
  </button>
</template>
