<script setup>
const props = defineProps({
  title: String,
  dueDate: String,
  status: String
})

const isCompleted = props.status === 'Completed'
</script>

<template>
  <div class="card">
    <div class="card-main">
      <div>
        <h4>{{ title }}</h4>
        <p>Due: {{ dueDate }}</p>
      </div>
      <span class="badge" :class="isCompleted ? 'completed' : 'pending'">
        {{ isCompleted ? 'Completed ✓' : 'Pending ⏰' }}
      </span>
    </div>
  </div>
</template>

<style scoped>
.card {
  background: #162032;
  border-left: 3px solid #2563eb;
  padding: 14px 16px;
  margin-bottom: 10px;
  border-radius: 10px;
  transition: background 0.2s ease;
}

.card:hover {
  background: #1a2a40;
}

.card-main {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 12px;
}

h4 {
  margin: 0 0 4px;
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
  white-space: nowrap;
}

.completed {
  background: rgba(16, 185, 129, 0.15);
  color: #34d399;
}

.pending {
  background: rgba(245, 158, 11, 0.15);
  color: #fbbf24;
}
</style>
