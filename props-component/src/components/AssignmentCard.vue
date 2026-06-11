<script setup>
defineProps({
  title: String,
  dueDate: String,
  status: String
})
</script>

<template>
  <div class="card">
    <h4>{{ title }}</h4>
    <p>Due: {{ dueDate }}</p>
    <p>Status: {{ status }}</p>
  </div>
</template>

<style scoped>
.card {
  background: white;
  border-left: 4px solid #2563eb;
  padding: 16px;
  margin-bottom: 12px;
  border-radius: 8px;
  box-shadow: 0 1px 4px rgba(0, 0, 0, 0.06);
  transition: transform 0.2s ease;
}

.card:hover {
  transform: translateX(4px);
}

h4 {
  margin: 0 0 4px;
  font-size: 1rem;
}

p {
  margin: 2px 0;
  color: #64748b;
  font-size: 0.875rem;
}
</style>