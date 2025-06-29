<script setup>
import { ref } from 'vue'
import CourseContent from '@/components/CourseContent.vue'
import CourseInfor from '@/components/CourseInfor.vue'
import CourseProgress from '@/components/CourseProgress.vue'
console.log('Hello')
const course = ref([
  {
    id: 1,
    title: 'Gioi thieu React',
    description: 'Tim hieu ve React va JSX',
    exerciseCompletionRate: 0.75,
    lesson: [
      {
        lessonTitle: 'React la gi?',
        duration: 15,
        status: 'completed',
        type: 'lesson',
      },
      {
        lessonTitle: 'Cai dat moi truong',
        duration: 20,
        status: 'completed',
        type: 'lesson',
      },
      {
        lessonTitle: 'JSX co ban',
        duration: 15,
        status: 'completed',
        type: 'lesson',
      },
      {
        lessonTitle: 'Kiểm tra Module 1',
        numberQuestions: 15,
        status: 'passed',
        type: 'test',
      },
    ],
  },
  {
    id: 2,
    title: 'Components va Props',
    description: 'Hoc cach tao va su dung components',
    exerciseCompletionRate: 0.25,
    lesson: [
      {
        lessonTitle: 'Functional Components',
        duration: 35,
        status: 'completed',
        type: 'lesson',
      },
      {
        lessonTitle: 'Props và PropTypes',
        duration: 20,
        status: 'notStarted',
        type: 'lesson',
      },
      {
        lessonTitle: 'Component Composition',
        duration: 35,
        status: 'notStarted',
        type: 'lesson',
      },
      {
        lessonTitle: 'Kiểm tra Module 2',
        numberQuestions: 15,
        status: 'notStarted',
        type: 'test',
      },
    ],
  },
  {
    id: 3,
    title: 'State va EventHandling',
    description: 'Tim hieu ve React va JSX',
    exerciseCompletionRate: 0,
    lesson: [
      {
        lessonTitle: 'useState Hook',
        duration: 40,
        status: 'notStarted',
        type: 'lesson',
      },
      {
        lessonTitle: 'Event Handling',
        duration: 30,
        status: 'notStarted',
        type: 'lesson',
      },
      {
        lessonTitle: 'Controlled Components',
        duration: 35,
        status: 'notStarted',
        type: 'lesson',
      },
      {
        lessonTitle: 'Kiểm tra Module 3',
        numberQuestions: 15,
        status: 'passed',
        type: 'test',
      },
    ],
  },
])
</script>

<template>
  <div class="course-page">
    <CourseInfor />
    <CourseContent />
    <CourseProgress />
  </div>
</template>

<style scoped>
.course-page {
  color: black;
  font-size: 16px;
  margin: 0 auto;
  max-width: 156rem;
  width: 100%;
  margin-left: auto;
  margin-right: auto;
}
</style>
