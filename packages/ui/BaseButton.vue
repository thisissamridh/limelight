<script setup lang="ts">
defineProps({
  disabled: {
    type: Boolean,
    default: false,
  },
  loading: {
    type: Boolean,
    default: false,
  },
  base: {
    type: Boolean,
    default: false,
  },

  primary: {
    type: Boolean,
    default: false,
  },
  secondary: {
    type: Boolean,
    default: false,
  },
  warning: {
    type: Boolean,
    default: false,
  },
  success: {
    type: Boolean,
    default: false,
  },
  accent: {
    type: Boolean,
    default: false,
  },
  danger: {
    type: Boolean,
    default: false,
  },
  tile: {
    type: Boolean,
    default: false,
  },
});
</script>

<template>
  <button
    class="text-center capitalize bg-red-400 font-montserrat block py-2 px-5 transition-all ease-in-out duration-300 hover:scale-105"
    :class="{
      rounded: !tile,
      'bg-primary font-montserrat text-light':
        !secondary && !warning && !success && !accent && !danger && !base,
      'bg-secondary text-light': secondary,
      'bg-yellow-600 text-white': warning,
      'bg-green-600 text-gray-600': success,
      'bg-accent text-light': accent,
      'bg-white hover:shadow-sm border border-red-500 text-red-500': danger,
      'bg-gray-400 cursor-not-allowed': disabled,
      'bg-gray-400 cursor-wait': loading,
      'bg-white': base,
    }"
    v-bind="$attrs"
  >
    <div class="flex justify-center gap-2">
      <slot> </slot>
      <div
        v-if="loading"
        style="border-top-color: transparent"
        class="w-5 h-5 border-4 border-white border-solid rounded-full animate-spin"
      ></div>
    </div>
  </button>
</template>
