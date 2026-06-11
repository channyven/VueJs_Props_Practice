<script setup>
import ActivityItem from './ActivityItem.vue'

defineProps({
  activities: Array
})
</script>

<template>
  <div>
    <h2>Recent Activities</h2>

    <ActivityItem
      v-for="(activity, index) in activities"
      :key="index"
      :activityName="activity.activityName"
      :date="activity.date"
      :type="activity.type"
    />
  </div>
</template>

<style scoped>
h2 {
  margin: 0 0 12px;
  font-size: 1.25rem;
}
</style>