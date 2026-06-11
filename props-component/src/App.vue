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
  avatar: 'https://placehold.co/150',
  fullName: 'Alex Morgan',
  email: 'alex@edu.com',
  batch: '2026-A',
  track: 'Frontend Development'
}

const stats = [
  { title: 'Lessons Completed', value: 12, icon: '📘' },
  { title: 'Exercises Done', value: 8, icon: '📝' },
  { title: 'Current Score', value: 92, icon: '🎯' },
  { title: 'Attendance Rate', value: '95%', icon: '📅' }
]

const assignments = [
  {
    title: 'Composition API Quiz',
    dueDate: 'June 15',
    status: 'Completed'
  },
  {
    title: 'Props Lab Exercise',
    dueDate: 'June 18',
    status: 'Pending'
  }
]

const activities = [
  {
    activityName: 'Submitted Exercise',
    date: '2 mins ago',
    type: 'Submit'
  },
  {
    activityName: 'Quiz Completed',
    date: '1 hour ago',
    type: 'Quiz'
  }
]
</script>

<template>
  <Header />

  <CourseInfo
    :courseName="course.courseName"
    :instructor="course.instructor"
    :progress="course.progress"
  />

  <StatsSection :stats="stats" />

  <div class="main-content">

    <StudentProfile
      :avatar="student.avatar"
      :fullName="student.fullName"
      :email="student.email"
      :batch="student.batch"
      :track="student.track"
    />

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
  background: linear-gradient(135deg, #0f172a 0%, #1e293b 50%, #334155 100%);
  font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
  color: #f1f5f9;
  line-height: 1.6;
  -webkit-font-smoothing: antialiased;
  overflow-x: hidden;
}

#app {
  max-width: 1280px;
  margin: 0 auto;
  padding: 32px;
  animation: fadeIn 0.6s ease-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.main-content {
  display: grid;
  grid-template-columns: 1fr 1.2fr 1fr;
  gap: 28px;
  margin-block: 32px;
  animation: slideUp 0.5s ease-out 0.2s both;
}

@keyframes slideUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.main-content > * {
  animation: cardFade 0.4s ease-out both;
}

.main-content > *:nth-child(1) { animation-delay: 0.3s; }
.main-content > *:nth-child(2) { animation-delay: 0.4s; }
.main-content > *:nth-child(3) { animation-delay: 0.5s; }

@keyframes cardFade {
  from {
    opacity: 0;
    transform: scale(0.95);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}

@media (max-width: 1024px) {
  #app {
    padding: 24px;
  }

  .main-content {
    grid-template-columns: 1fr 1fr;
    gap: 24px;
  }
}

@media (max-width: 640px) {
  #app {
    padding: 16px;
  }

  .main-content {
    grid-template-columns: 1fr;
    gap: 20px;
    margin-block: 24px;
  }
}
</style>