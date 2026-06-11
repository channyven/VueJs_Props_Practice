<script setup>
import AssignmentCard from './AssignmentCard.vue'

defineProps({
  assignments: Array
})
</script>

<template>
  <div class="container">
    <div class="header-row">
      <div class="title-wrap">
        <span class="title-icon">📋</span>
        <h2>Assignments</h2>
      </div>
      <span class="view-all">View all</span>
    </div>

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
.container {
  background: #0f2044;
  border-radius: 16px;
  padding: 24px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.25);
}

.header-row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 18px;
}

.title-wrap {
  display: flex;
  align-items: center;
  gap: 10px;
}

.title-icon {
  font-size: 1.25rem;
}

h2 {
  margin: 0;
  font-size: 1.1rem;
  font-weight: 700;
  color: #f1f5f9;
}

.view-all {
  font-size: 0.8rem;
  color: #3b82f6;
  cursor: pointer;
  font-weight: 500;
}

.view-all:hover {
  text-decoration: underline;
}
</style>
