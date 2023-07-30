<script setup lang="ts">
const { defaultTransition, twitterBorderColor } = useTailwindConfig();

const wrapperClasses = computed(
  () => `${defaultTransition} ${twitterBorderColor}`
);
</script>

<template>
  <div
    class="p-3 border-b cursor-pointer hover:bg-gray-100 hover:dark:bg-dim-300 "
    :class="wrapperClasses"
  >
    <slot></slot>
  </div>
</template>
