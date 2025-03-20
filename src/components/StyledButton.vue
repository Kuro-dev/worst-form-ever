<template>
  <div class="input-group">
    <label :for="id" class="input-label">{{ label }}</label>
    <input
        :id="id"
        :type="type"
        :placeholder="placeholder"
        v-model="inputValue"
        class="styled-input"
    />
  </div>
</template>

<script setup lang="ts">
import { ref, defineProps, defineEmits } from 'vue';

const props = defineProps<{
  id: string;
  label: string;
  type?: string;
  placeholder?: string;
  modelValue: string;
}>();

const emit = defineEmits(['update:modelValue']);

const inputValue = ref(props.modelValue);

watch(inputValue, (newValue) => {
  emit('update:modelValue', newValue);
});
</script>

<style scoped>
.input-group {
  display: flex;
  flex-direction: column;
  margin-bottom: 1rem;
}

.input-label {
  margin-bottom: 0.5rem;
  font-size: 1rem;
  font-weight: 500;
  color: #4b5563;
}

.styled-input {
  padding: 0.75rem;
  border: 1px solid #d1d5db;
  border-radius: 0.5rem;
  background-color: #f9fafb;
  font-size: 1rem;
  color: #374151;
}

.styled-input:focus {
  outline: none;
  border-color: #3b82f6;
  background-color: #ffffff;
}
</style>
