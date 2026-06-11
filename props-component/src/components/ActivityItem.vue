<script setup>
defineProps({
  activityName: String,
  date: String,
  type: String
})
</script>

<template>
  <div class="item">
    <h4>{{ activityName }}</h4>
    <p>{{ date }}</p>
    <p>{{ type }}</p>
  </div>
</template>

<style scoped>
.item {
  background: white;
  padding: 14px;
  margin-bottom: 12px;
  border-radius: 8px;
  border-left: 4px solid #10b981;
  box-shadow: 0 1px 4px rgba(0, 0, 0, 0.06);
  transition: transform 0.2s ease;
}

.item:hover {
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