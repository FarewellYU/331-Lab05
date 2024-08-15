<script setup lang="ts">
import Student from '@/types/Student'
defineProps<{
  student: Student
}>()
</script>
 
<template>
  <div class="flex justify-center">
    <div class="p-5 w-64 cursor-pointer border border-gray-600 mb-4 hover:scale-[1.01] hover:shadow-sp transition-transform duration-300">
      <h2>{{ student.name }} {{ student.surname }}</h2>
      <span>GPA: {{ student.gpa }}</span>
    </div>
  </div>
</template>
 
<style scoped>
/* .student-card {
  padding: 20px;
  width: 250px;
  cursor: pointer;
  border: 1px solid #39495c;
  margin-bottom: 18px;
}
.student-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
} */
</style>
 