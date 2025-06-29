<script setup>
import { ref } from 'vue'
import LessonItem from '@/components/LessonItem.vue'
const data = ref({
  lessonTitle: 'React là gì?',
  duration: 15,
  status: 'completed',
  type: 'lesson',
})
</script>

<template>
  <LessonItem :lesson="data" />
</template>

<style></style>
