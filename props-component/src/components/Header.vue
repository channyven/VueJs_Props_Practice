<template>
  <header class="header">
    <div class="icon-box">
      <span class="cap">🎓</span>
    </div>
    <div class="text">
      <h1>Vue.js Props Practice Lab Dashboard</h1>
      <p>Track your progress, assignments, and activities in one place.</p>
    </div>
  </header>
</template>

<style scoped>
.header {
  background: linear-gradient(135deg, #2563eb 0%, #1d4ed8 60%, #1e40af 100%);
  color: white;
  padding: 32px 36px;
  border-radius: 16px;
  box-shadow: 0 8px 32px rgba(37, 99, 235, 0.35);
  display: flex;
  align-items: center;
  gap: 24px;
  position: relative;
  overflow: hidden;
}

.header::before {
  content: '';
  position: absolute;
  top: -40px;
  right: -40px;
  width: 200px;
  height: 200px;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 50%;
}

.header::after {
  content: '';
  position: absolute;
  bottom: -60px;
  right: 80px;
  width: 160px;
  height: 160px;
  background: rgba(255, 255, 255, 0.04);
  border-radius: 50%;
}

.icon-box {
  width: 72px;
  height: 72px;
  background: rgba(255, 255, 255, 0.18);
  border-radius: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  backdrop-filter: blur(8px);
}

.cap {
  font-size: 36px;
}

.text {
  position: relative;
  z-index: 1;
}

h1 {
  margin: 0 0 6px;
  font-size: 1.6rem;
  font-weight: 700;
  line-height: 1.2;
}

p {
  margin: 0;
  font-size: 0.95rem;
  opacity: 0.85;
  line-height: 1.5;
}
</style>
