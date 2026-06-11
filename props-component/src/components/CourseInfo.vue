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

    <p>Instructor: {{ instructor }}</p>

    <div class="progress-bar">
      <div
        class="progress-fill"
        :style="{ width: progress + '%' }"
      ></div>
    </div>

    <p>{{ progress }}% Completed</p>
  </div>
</template>

<style scoped>
.course-card {
  background: white;
  padding: 24px;
  border-radius: 12px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.08);
}

h2 {
  margin: 0 0 8px;
  font-size: 1.25rem;
}

p {
  margin: 0 0 12px;
  color: #64748b;
}

.progress-bar {
  height: 10px;
  background: #e2e8f0;
  border-radius: 10px;
  overflow: hidden;
}

.progress-fill {
  height: 100%;
  background: linear-gradient(90deg, #2563eb, #3b82f6);
  border-radius: 10px;
  transition: width 0.4s ease;
}
</style>