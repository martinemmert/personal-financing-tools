<script setup lang="ts">
import { TransitionChild, DialogOverlay } from "@headlessui/vue";
</script>

<template>
  <TransitionChild
    as="template"
    enter="ease-out duration-300"
    enter-from="opacity-0"
    enter-to="opacity-100"
    leave="ease-in duration-200"
    leave-from="opacity-100"
    leave-to="opacity-0"
  >
    <DialogOverlay class="backdrop" />
  </TransitionChild>
</template>

<style lang="postcss">
.backdrop {
  @apply fixed inset-0 bg-gray-500 bg-opacity-75 transition-opacity;
}
</style>
