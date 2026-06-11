<script setup>
const props = defineProps({
  fullName: String,
  email: String,
  batch: String,
  track: String
})

const initials = props.fullName
  ?.split(' ')
  .map(n => n[0])
  .join('')
  .toUpperCase()
</script>

<template>
  <div class="profile">
    <div class="avatar">
      <span>{{ initials }}</span>
    </div>
    <h3>{{ fullName }}</h3>
    <span class="badge">Student</span>
    <div class="info">
      <div class="info-row">
        <span class="info-icon">✉️</span>
        <span>{{ email }}</span>
      </div>
      <div class="info-row">
        <span class="info-icon">👥</span>
        <span>Batch: {{ batch }}</span>
      </div>
      <div class="info-row">
        <span class="info-icon">💻</span>
        <span>Track: {{ track }}</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.profile {
  background: #0f2044;
  border-radius: 16px;
  padding: 28px 20px;
  text-align: center;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.25);
  color: white;
  min-width: 210px;
  width: 240px;
}

.avatar {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  background: linear-gradient(135deg, #6366f1, #2563eb);
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 14px;
  font-size: 1.5rem;
  font-weight: 800;
  color: white;
  border: 3px solid rgba(255, 255, 255, 0.2);
}

h3 {
  margin: 0 0 8px;
  font-size: 1.15rem;
  font-weight: 700;
}

.badge {
  display: inline-block;
  background: rgba(99, 102, 241, 0.25);
  color: #a5b4fc;
  font-size: 0.75rem;
  font-weight: 600;
  padding: 3px 12px;
  border-radius: 20px;
  margin-bottom: 18px;
}

.info {
  display: flex;
  flex-direction: column;
  gap: 10px;
  text-align: left;
}

.info-row {
  display: flex;
  align-items: flex-start;
  gap: 10px;
  font-size: 0.875rem;
  color: #94a3b8;
}

.info-icon {
  font-size: 1rem;
  flex-shrink: 0;
  margin-top: 1px;
}
</style>
