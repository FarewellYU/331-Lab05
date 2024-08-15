<script setup lang="ts">
import { type Event } from '@/types';
defineProps<{
  event: Event
}>()
// const event = ref({
//   id: 5928101,
//   category: 'animal welfare',
//   title: 'Cat Adoption Day',
//   description: 'Find your new feline friend at this event.',
//   location: 'Meow Town',
//   date: 'January 28, 2022',
//   time: '12:00',
//   petsAllowed: true,
//   organizer: 'Kat Laydee'
// })
</script>

<template>
  <div class="p-5 w-64 cursor-pointer border border-gray-600 mb-4 flex flex-col items-end hover:scale-[1.01] hover:shadow-sp transition-transform duration-300">
    <h2>{{ event.category }}</h2>
    <span>{{ event.organizer }}</span>
  </div>
</template>

<style scoped>
/* .event-details {
  padding: 20px;
  width: 250px;
  cursor: pointer;
  border: 1px solid #39495c;
  margin-bottom: 18px;
  display: flex;
  flex-direction: column;
  align-items: flex-end;
}
.event-details:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
} */
</style>
