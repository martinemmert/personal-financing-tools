<script setup lang="ts">
import { useField } from "vee-validate";
import TextInputMessage from "_components/atoms/text-input-message.vue";

type Props = {
  id?: string;
  name: string;
};

const props = defineProps<Props>();

const {
  value: fieldValue,
  meta,
  errorMessage,
} = useField<boolean>(props.name, undefined, {
  type: "checkbox",
});
</script>

<template>
  <div class="relative flex items-start">
    <div class="flex h-5 items-center">
      <input
        type="checkbox"
        :id="props.id ?? props.name"
        :name="props.name"
        v-model="fieldValue"
        class="h-4 w-4 rounded border-gray-300 text-indigo-600 focus:ring-indigo-500"
      />
    </div>
    <div class="ml-3 items-center text-sm">
      <label :for="props.id ?? props.name" class="text-gray-700">
        <slot></slot>
      </label>
      <TextInputMessage v-if="errorMessage" class="mt-1" variant="negative">
        {{ errorMessage }}
      </TextInputMessage>
    </div>
  </div>
</template>
