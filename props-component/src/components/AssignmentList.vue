<script setup>
import AssignmentCard from './AssignmentCard.vue'

defineProps({
  assignments: Array
})
</script>

<template>
  <div>
    <h2>Assignments</h2>

    <AssignmentCard
      v-for="(assignment, index) in assignments"
      :key="index"
      :title="assignment.title"
      :dueDate="assignment.dueDate"
      :status="assignment.status"
    />
  </div>
</template>

<style scoped>
h2 {
  margin: 0 0 12px;
  font-size: 1.25rem;
}
</style>