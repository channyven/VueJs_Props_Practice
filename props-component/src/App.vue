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
  background: linear-gradient(135deg, #f5f7fb 0%, #eef1f7 100%);
  font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
  color: #2c3e50;
  line-height: 1.6;
  -webkit-font-smoothing: antialiased;
}

#app {
  max-width: 1200px;
  margin: 0 auto;
  padding: 24px;
}

.main-content {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 24px;
  margin-block: 24px;
}

@media (max-width: 1024px) {
  .main-content {
    grid-template-columns: 1fr 1fr;
  }
}

@media (max-width: 640px) {
  .main-content {
    grid-template-columns: 1fr;
  }
}
</style>