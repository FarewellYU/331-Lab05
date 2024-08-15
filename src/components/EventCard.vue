<script setup lang="ts">
import { type Event } from '@/types'
import { RouterLink } from 'vue-router'
defineProps<{
  event: Event
}>()
</script>

<template>
  <RouterLink class="text-blue-500 no-underline hover:underline" :to="{ name: 'event-detail-view', params: { id: event.id } }">
    <div class="cursor-pointer border border-gray-600 p-5 w-64 mb-4 hover:scale-[1.01] hover:shadow-sp transition-transform duration-300">
      <h2>{{ event.title }}</h2>
      <span>@{{ event.time }} on {{ event.date }}</span>
    </div>
  </RouterLink>
</template>

<style scoped>
/* .event-card {
  padding: 20px;
  width: 250px;
  cursor: pointer;
  border: 1px solid #39495c;
  margin-bottom: 18px;
}
.event-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}

.event-link {
  text-decoration: none;
  color: #54a3f3;
} */
</style>
