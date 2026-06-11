<script setup>
defineProps({
  title: String,
  value: [String, Number],
  icon: String
})
</script>

<template>
  <div class="stat-card">
    <div class="icon">{{ icon }}</div>

    <h2>{{ value }}</h2>

    <p>{{ title }}</p>
  </div>
</template>

<style scoped>
.stat-card {
  background: white;
  border-radius: 12px;
  padding: 24px;
  text-align: center;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.08);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.stat-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 16px rgba(0, 0, 0, 0.12);
}

.icon {
  font-size: 32px;
  margin-bottom: 8px;
}

h2 {
  margin: 0;
  color: #2563eb;
  font-size: 1.75rem;
}

p {
  margin: 4px 0 0;
  color: #64748b;
  font-size: 0.875rem;
}
</style>