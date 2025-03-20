<template>
  <form class="styled-form" @submit.prevent="handleSubmit">
    <slot></slot>
    <button type="submit" class="submit-button">Submit</button>
  </form>
</template>

<script setup lang="ts">
const handleSubmit = (): void => {
  console.log("Form submitted");
};
</script>

<style scoped>
.styled-form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  padding: 2rem;
  border-radius: 0.5rem;
  background-color: #f3f4f6;
  border: 1px solid #e5e7eb;
  max-width: 400px;
  margin: 0 auto;
}

.submit-button {
  padding: 0.75rem;
  background-color: #3b82f6;
  color: white;
  border: none;
  border-radius: 0.5rem;
  cursor: pointer;
}

.submit-button:hover {
  background-color: #2563eb;
}
</style>
