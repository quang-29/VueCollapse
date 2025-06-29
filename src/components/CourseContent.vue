<script setup>
import { ref } from 'vue'
import { CircleCheck, Notebook, TrophyBase, VideoPlay } from '@element-plus/icons-vue'
const courses = ref([
  {
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
      {
        lessonTitle: 'Cài đặt môi trường',
        duration: 20,
        status: 'completed',
        type: 'lesson',
      },
      {
        lessonTitle: 'JSX cơ bản',
        duration: 15,
        status: 'notStarted',
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
    title: 'Components và Props',
    description: 'Tìm hiểu cách tạo và sử dụng components',
    exerciseCompletionRate: 25,
    lessons: [
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
    title: 'State và Event Handling',
    description: 'Tìm hiểu về State và Event Handling',
    exerciseCompletionRate: 0,
    lessons: [
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
        status: 'notStarted',
        type: 'test',
      },
    ],
  },
  {
    id: 4,
    title: 'Hooks nâng cao trong React',
    description: 'Khám phá useEffect, useRef, useMemo và custom hooks',
    exerciseCompletionRate: 0,
    lessons: [
      {
        lessonTitle: 'Tìm hiểu useEffect',
        duration: 30,
        status: 'notStarted',
        type: 'lesson',
      },
      {
        lessonTitle: 'Sử dụng useRef',
        duration: 25,
        status: 'notStarted',
        type: 'lesson',
      },
      {
        lessonTitle: 'Tối ưu hóa với useMemo & useCallback',
        duration: 35,
        status: 'notStarted',
        type: 'lesson',
      },
      {
        lessonTitle: 'Tạo custom hook đầu tiên',
        duration: 40,
        status: 'notStarted',
        type: 'lesson',
      },
      {
        lessonTitle: 'Kiểm tra Module 4',
        numberQuestions: 12,
        status: 'notStarted',
        type: 'test',
      },
    ],
  },
  {
    id: 5,
    title: 'Routing và Quản lý trạng thái',
    description: 'Học cách điều hướng với React Router và quản lý trạng thái ứng dụng',
    exerciseCompletionRate: 0,
    lessons: [
      {
        lessonTitle: 'Giới thiệu React Router',
        duration: 25,
        status: 'notStarted',
        type: 'lesson',
      },
      {
        lessonTitle: 'Nested routes và điều hướng',
        duration: 30,
        status: 'notStarted',
        type: 'lesson',
      },
      {
        lessonTitle: 'Tìm hiểu Context API',
        duration: 35,
        status: 'notStarted',
        type: 'lesson',
      },
      {
        lessonTitle: 'Quản lý trạng thái với Redux',
        duration: 40,
        status: 'notStarted',
        type: 'lesson',
      },
      {
        lessonTitle: 'Kiểm tra Module 5',
        numberQuestions: 15,
        status: 'notStarted',
        type: 'test',
      },
    ],
  },
])
</script>

<template>
  <div class="course-main">
    <div class="course-title">
      <h2 class="course-header">Nội dung khóa học</h2>
    </div>
    <div class="demo-collapse">
      <el-collapse class="no-border" accordion>
        <el-collapse-item
          v-for="course in courses"
          :key="course.id"
          :name="course.title"
          class="el-collapse-item"
        >
          <template #title="{ isActive }">
            <div :class="['title-wrapper', { 'is-active': isActive }]">
              <div class="course-heading">
                <div class="course-id">
                  <p>{{ course.id }}</p>
                </div>
                <div class="course-details">
                  <p class="course-title">{{ course.title }}</p>
                  <p class="course-description">{{ course.description }}</p>
                </div>
              </div>
              <div class="course-exercise-completion">
                <p>{{ course.exerciseCompletionRate }} %</p>
              </div>
              <!-- <span class="icon-ele">
                {{ isActive ? 'Expanded' : 'Collapsed' }}
              </span> -->
            </div>
          </template>
          <div v-for="lesson in course.lessons" :key="lesson.lessonTitle" class="lesson-item">
            <div class="lesson-info">
              <div>
                <p v-if="lesson.status === 'completed' && lesson.type === 'lesson'">
                  <el-icon class="check-icon" :style="{ color: '#4caf50', fontSize: '1.25rem' }">
                    <CircleCheck />
                  </el-icon>
                </p>
                <p v-if="lesson.status === 'notStarted' && lesson.type === 'lesson'">
                  <el-icon class="check-icon" :style="{ color: '#6b7280', fontSize: '1.25rem' }">
                    <Stopwatch />
                  </el-icon>
                </p>
                <p v-if="lesson.type === 'test'">
                  <el-icon class="check-icon" :style="{ color: 'orange', fontSize: '1.25rem' }">
                    <TrophyBase />
                  </el-icon>
                </p>
              </div>

              <div>
                <p class="lesson-title">{{ lesson.lessonTitle }}</p>
                <p v-if="lesson.type === 'lesson'" class="lesson-duration">
                  <el-icon><Clock /></el-icon>
                  <span>{{ lesson.duration }} phút</span>
                </p>
                <p v-if="lesson.type === 'test'" class="lesson-question-count">
                  <span>{{ lesson.numberQuestions }} câu hỏi</span>
                </p>
              </div>
            </div>
            <div class="lesson-status">
              <p
                v-if="lesson.type === 'lesson' && lesson.status === 'completed'"
                class="lesson-completed-tag"
              >
                Hoàn thành
              </p>
              <button
                v-else-if="lesson.type === 'lesson' && lesson.status === 'notStarted'"
                class="lesson-btn-learn"
              >
                <el-icon><VideoPlay /></el-icon>
                <span>Học</span>
              </button>
              <p
                v-if="lesson.type === 'test' && lesson.status === 'passed'"
                class="test-completed-tag"
              >
                Đã qua (85%)
              </p>
              <div
                v-else-if="lesson.type === 'test' && lesson.status === 'notStarted'"
                class="lesson-test"
              >
                <span class="test-not-started-tag">Chưa làm</span>
                <button class="lesson-btn-do">Làm bài</button>
              </div>
            </div>
          </div>
        </el-collapse-item>
      </el-collapse>
    </div>
  </div>
</template>

<style scoped>
.title-wrapper {
  display: flex;
  align-items: center;
  gap: 1rem;
  width: 100%;
  flex-wrap: wrap;
}
.el-collapse-item {
  padding: 20px 0 20px 20px;
  border-radius: 0.5rem;
  border-bottom: 1px solid #e5e7eb;
  margin-top: 10px;
}
.demo-collapse {
  height: auto;
}

.title-wrapper.is-active {
  color: var(--el-color-primary);
}
.course-main {
  margin-top: 20px;
  border-radius: 0.5rem;
  border: 1px solid #ccc;
  padding: 1.5rem;
}
.course-header {
  font-weight: 600;
  font-size: 1.5rem;
  line-height: 2rem;
}
.title-wrapper {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.course-heading {
  display: flex;
  align-items: center;
  gap: 1rem;
}
.course-id {
  font-size: 1.15rem;
  line-height: 2rem;
  color: #2563eb;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background-color: #dbeafe;
  display: flex;
  align-items: center;
  justify-content: center;
}
.course-id p {
  font-weight: 600;
}
.course-heading .course-title {
  font-weight: 500;
  font-size: 1.25rem;
  line-height: 1.5rem;
}

.course-description {
  font-size: 1rem;
  line-height: 1.5rem;
  color: #222;
  letter-spacing: 0.5px;
  margin-top: 5px;
}
.course-details {
  font-size: 1.25rem;
  line-height: 1.5rem;
}
.course-exercise-completion {
  width: 55px;
  height: 25px;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 1px solid #dcdfe6;
  border-radius: 20px;
}
.course-exercise-completion p {
  font-size: 0.875rem;
  font-weight: 600;
  line-height: 1.5rem;
}
.lesson-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.75rem;
  border-bottom: 1px solid #e5e7eb;
  border: 1px solid #dcdfe6;
  margin-left: 50px;
  margin-top: 10px;
  border-radius: 0.5rem;
  cursor: pointer;
}
.lesson-item:hover {
  background-color: #f9fafb;
}
.lesson-info {
  display: flex;
  align-items: center;
  gap: 1rem;
}
.lesson-title {
  font-size: 1rem;
  line-height: 1.5rem;
  font-weight: 500;
}

.lesson-duration,
.lesson-question-count {
  font-size: 1rem;
  line-height: 1rem;
  color: #6b7280;
  margin-top: 5px;
}
.el-collapse-item__wrap {
  border: none;
}
.icon-ele {
  margin: 0 8px 0 auto;
  color: #409eff;
}
.lesson-duration,
.lesson-question-count {
  display: flex;
  align-items: center;
  gap: 0.25rem;
}
.lesson-btn-learn,
.lesson-btn-do {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: black;
  padding-left: 0.75rem;
  padding-right: 0.75rem;
  padding-top: 0.25rem;
  padding-bottom: 0.25rem;
  border: none;
  border-radius: 0.375rem;
  background-color: #f3f4f6;
  cursor: pointer;
}
.lesson-btn-learn:hover,
.lesson-btn-do:hover {
  background-color: #e5e7eb;
}
.lesson-test {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}
.lesson-completed-tag,
.test-completed-tag {
  color: #166534;
  font-weight: 600;
  font-size: 0.875rem;
  line-height: 1.5rem;
  padding-top: 0.125rem;
  padding-bottom: 0.125rem;
  padding-left: 0.625rem;
  padding-right: 0.625rem;
  background-color: #dcfce7;
  border-radius: 0.375rem;
}
.test-not-started-tag {
  color: #6b7280;
  font-weight: 600;
  font-size: 0.875rem;
  line-height: 1.5rem;
  padding-top: 0.125rem;
  padding-bottom: 0.125rem;
  padding-left: 0.625rem;
  padding-right: 0.625rem;
  background-color: #f3f4f6;
  border-radius: 0.475rem;
}
</style>
