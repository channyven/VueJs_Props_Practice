<script setup>
import StatCard from './StatCard.vue'

defineProps({
  stats: Array
})
</script>

<template>
  <div class="stats-section">
    <StatCard
      v-for="(stat, index) in stats"
      :key="index"
      :title="stat.title"
      :value="stat.value"
      :icon="stat.icon"
      :color="stat.color"
      :bgColor="stat.bgColor"
    />
  </div>
</template>

<style scoped>
.stats-section {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 20px;
}

@media (max-width: 1024px) {
  .stats-section {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 640px) {
  .stats-section {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
