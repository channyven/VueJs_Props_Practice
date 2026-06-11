<script setup>
defineProps({
  title: String,
  value: [String, Number],
  icon: String,
  color: { type: String, default: '#2563eb' },
  bgColor: { type: String, default: '#eff6ff' }
})
</script>

<template>
  <div class="stat-card">
    <div class="icon-wrap" :style="{ background: bgColor }">
      <span class="icon">{{ icon }}</span>
    </div>
    <h2 :style="{ color }">{{ value }}</h2>
    <p>{{ title }}</p>
    <div class="underline" :style="{ background: color }"></div>
  </div>
</template>

<style scoped>
.stat-card {
  background: white;
  border-radius: 16px;
  padding: 28px 20px 24px;
  text-align: center;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 4px;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  cursor: default;
}

.stat-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 10px 28px rgba(0, 0, 0, 0.13);
}

.icon-wrap {
  width: 60px;
  height: 60px;
  border-radius: 14px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 12px;
}

.icon {
  font-size: 28px;
}

h2 {
  margin: 0;
  font-size: 2.1rem;
  font-weight: 800;
  line-height: 1;
}

p {
  margin: 6px 0 10px;
  color: #64748b;
  font-size: 0.875rem;
  line-height: 1.4;
}

.underline {
  width: 28px;
  height: 3px;
  border-radius: 2px;
  margin-top: 4px;
}
</style>
