<script setup>
import Header from './components/Header.vue'
import CourseInfo from './components/CourseInfo.vue'
import StatsSection from './components/StatsSection.vue'
import StudentProfile from './components/StudentProfile.vue'
import AssignmentList from './components/AssignmentList.vue'
import ActivityTimeline from './components/ActivityTimeline.vue'
import Footer from './components/Footer.vue'

const course = {
  courseName: 'Frontend Frameworks (Vue 3)',
  instructor: 'Prof. Evans',
  progress: 60
}

const student = {
  fullName: 'Alex Morgan',
  email: 'alex@edu.com',
  batch: '2026-A',
  track: 'Frontend Development'
}

const stats = [
  { title: 'Lessons Completed', value: 12, icon: '📘', color: '#2563eb', bgColor: '#eff6ff' },
  { title: 'Exercises Done',    value: 8,  icon: '📝', color: '#f97316', bgColor: '#fff7ed' },
  { title: 'Current Score',     value: 92, icon: '🎯', color: '#e11d48', bgColor: '#fff1f2' },
  { title: 'Attendance Rate',   value: '95%', icon: '📅', color: '#7c3aed', bgColor: '#f5f3ff' }
]

const assignments = [
  { title: 'Composition API Quiz', dueDate: 'June 15', status: 'Completed' },
  { title: 'Props Lab Exercise',   dueDate: 'June 18', status: 'Pending'   }
]

const activities = [
  { activityName: 'Submitted Exercise', date: '2 mins ago', type: 'Submit' },
  { activityName: 'Quiz Completed',     date: '1 hour ago', type: 'Quiz'   }
]
</script>

<template>
  <div class="top-row">
    <Header />
    <CourseInfo
      :courseName="course.courseName"
      :instructor="course.instructor"
      :progress="course.progress"
    />
  </div>

  <div class="middle-row">
    <StatsSection :stats="stats" />
    <StudentProfile
      :fullName="student.fullName"
      :email="student.email"
      :batch="student.batch"
      :track="student.track"
    />
  </div>

  <div class="bottom-row">
    <AssignmentList :assignments="assignments" />
    <ActivityTimeline :activities="activities" />
  </div>

  <Footer />
</template>

<style>
*,
*::before,
*::after {
  box-sizing: border-box;
}

body {
  margin: 0;
  min-height: 100vh;
  background: linear-gradient(160deg, #0d1b2e 0%, #0f2044 50%, #162032 100%);
  font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
  color: #f1f5f9;
  line-height: 1.6;
  -webkit-font-smoothing: antialiased;
  overflow-x: hidden;
}

#app {
  max-width: 1320px;
  margin: 0 auto;
  padding: 32px;
  display: flex;
  flex-direction: column;
  gap: 24px;
  animation: fadeIn 0.5s ease-out;
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(16px); }
  to   { opacity: 1; transform: translateY(0); }
}

/* Row 1: Header (60%) + CourseInfo (40%) */
.top-row {
  display: grid;
  grid-template-columns: 3fr 2fr;
  gap: 24px;
  align-items: stretch;
}

/* Row 2: 4 stat cards + student profile */
.middle-row {
  display: grid;
  grid-template-columns: 1fr auto;
  gap: 24px;
  align-items: start;
}

/* Row 3: Assignments + Activities */
.bottom-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 24px;
}

@media (max-width: 1100px) {
  .top-row {
    grid-template-columns: 1fr 1fr;
  }

  .middle-row {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 768px) {
  #app {
    padding: 20px;
    gap: 20px;
  }

  .top-row,
  .bottom-row {
    grid-template-columns: 1fr;
  }

  .middle-row {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 480px) {
  #app {
    padding: 16px;
  }
}
</style>
