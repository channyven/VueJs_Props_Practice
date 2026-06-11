<script setup>
defineProps({
  courseName: String,
  instructor: String,
  progress: Number
})
</script>

<template>
  <div class="course-card">
    <h2>{{ courseName }}</h2>
    <p class="instructor"><span>Instructor:</span> <strong>{{ instructor }}</strong></p>
    <div class="progress-row">
      <div class="progress-bar">
        <div class="progress-fill" :style="{ width: progress + '%' }"></div>
      </div>
      <span class="pct">{{ progress }}%</span>
    </div>
    <p class="completed-label">{{ progress }}% Completed</p>
  </div>
</template>

<style scoped>
.course-card {
  background: white;
  padding: 28px 32px;
  border-radius: 16px;
  box-shadow: 0 4px 24px rgba(0, 0, 0, 0.1);
  display: flex;
  flex-direction: column;
  justify-content: center;
}

h2 {
  margin: 0 0 10px;
  font-size: 1.3rem;
  font-weight: 700;
  color: #7c3aed;
}

.instructor {
  margin: 0 0 18px;
  font-size: 0.95rem;
  color: #374151;
}

.instructor strong {
  color: #2563eb;
  font-weight: 600;
}

.progress-row {
  display: flex;
  align-items: center;
  gap: 14px;
  margin-bottom: 10px;
}

.progress-bar {
  flex: 1;
  height: 10px;
  background: #e2e8f0;
  border-radius: 10px;
  overflow: hidden;
}

.progress-fill {
  height: 100%;
  background: linear-gradient(90deg, #2563eb, #3b82f6);
  border-radius: 10px;
  transition: width 0.6s ease;
}

.pct {
  font-weight: 700;
  font-size: 1rem;
  color: #2563eb;
  min-width: 40px;
  text-align: right;
}

.completed-label {
  margin: 0;
  color: #94a3b8;
  font-size: 0.85rem;
}
</style>
