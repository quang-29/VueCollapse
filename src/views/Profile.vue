<script setup>
import CourseItem from '@/components/CourseItem.vue'
import { ref } from 'vue'
const data = ref({
  id: 1,
  title: 'Giới thiệu React',
  description: 'Tìm hiểu về React và JSX',
  exerciseCompletionRate: 75,
  lessons: [
    {
      lessonTitle: 'React là gì?',
      duration: 15,
      status: 'completed',
      type: 'lesson',
    },
  ],
})
</script>

<template>
  <CourseItem :course="data" />
</template>

<style></style>
