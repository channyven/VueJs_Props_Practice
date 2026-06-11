<script setup>
defineProps({
  activityName: String,
  date: String,
  type: String
})
</script>

<template>
  <div class="item">
    <div class="item-left">
      <div class="dot"></div>
      <div>
        <h4>{{ activityName }}</h4>
        <p>{{ date }}</p>
      </div>
    </div>
    <span class="badge">{{ type }}</span>
  </div>
</template>

<style scoped>
.item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 12px;
  background: #162032;
  padding: 14px 16px;
  margin-bottom: 10px;
  border-radius: 10px;
  border-left: 3px solid #10b981;
  transition: background 0.2s ease;
}

.item:hover {
  background: #1a2a40;
}

.item-left {
  display: flex;
  align-items: center;
  gap: 12px;
}

.dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: #10b981;
  flex-shrink: 0;
}

h4 {
  margin: 0 0 3px;
  font-size: 0.95rem;
  font-weight: 600;
  color: #e2e8f0;
}

p {
  margin: 0;
  color: #64748b;
  font-size: 0.8rem;
}

.badge {
  flex-shrink: 0;
  font-size: 0.72rem;
  font-weight: 600;
  padding: 4px 10px;
  border-radius: 20px;
  background: rgba(16, 185, 129, 0.15);
  color: #34d399;
  white-space: nowrap;
}
</style>
