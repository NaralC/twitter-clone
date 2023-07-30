<script setup lang="ts">
const { defaultTransition } = useTailwindConfig();

const props = defineProps({
  active: {
    type: Boolean,
    default: false,
  },
});

const textClasses = computed(() =>
  props.active ? "font-bold underline text-blue-500 dark:text-sky-500" : "font-semibold"
);

const iconClasses = computed(() =>
  props.active ? "text-blue-500 dark:text-sky-500" : ""
);
</script>

<template>
  <nuxt-link
    to="#"
    class="flex items-center p-3 text-black rounded-full w-min hover:bg-gray-200 dark:hover:bg-dim-200 dark:text-white saturate-150"
    :class="defaultTransition"
  >
    <div class="w-6 h-6 mb-[6px] text-dark" :class="iconClasses">
      <slot name="icon"></slot>
    </div>
    <div class="hidden ml-4 text-xl xl:block" :class="textClasses">
      <slot name="name"></slot>
    </div>
  </nuxt-link>
</template>
