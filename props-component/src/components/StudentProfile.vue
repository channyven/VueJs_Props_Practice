<script setup>
defineProps({
  avatar: String,
  fullName: String,
  email: String,
  batch: String,
  track: String
})
</script>

<template>
  <div class="profile">
    <img :src="avatar" width="120" />
    <h3>{{ fullName }}</h3>
    <p>{{ email }}</p>
    <p>Batch: {{ batch }}</p>
    <p>Track: {{ track }}</p>
  </div>
</template>

<style scoped>
.profile {
  background: white;
  border-radius: 12px;
  padding: 24px;
  text-align: center;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.08);
}

.profile img {
  border-radius: 50%;
  border: 4px solid #e2e8f0;
  margin-bottom: 12px;
}

h3 {
  margin: 0 0 4px;
  font-size: 1.125rem;
}

p {
  margin: 4px 0;
  color: #64748b;
  font-size: 0.875rem;
}
</style>