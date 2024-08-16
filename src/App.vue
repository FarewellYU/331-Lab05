<!-- src/App.vue -->
<script setup lang="ts">
import { RouterLink, RouterView, useRouter, useRoute } from 'vue-router'
import { useMessageStore } from './stores/message';
import { storeToRefs } from 'pinia';
import { ref } from 'vue'

const perPage = ref(2)
const router = useRouter()
const route = useRoute()
const store = useMessageStore()
const { message } = storeToRefs(store)

function updatePerPage(size: number) {
  perPage.value = size
  router.push({ name: 'event-list-view', query: { page: 1, perPage: size } })
}
</script>

<template>
  <speedInsights/>
  <div class="text-center font-sans text-gray-700 antialiased">
    <header>
      <div id="flashMessage" class="animate-fade" v-if="message">
        <h4>{{ message }}</h4>
      </div>
      <h1>Deploy with Vercel</h1>
      <div class="wrapper">
        <nav class="py-6 flex space-x-4 justify-center">
          <RouterLink class="font-bold text-gray-700" exact-active-class="text-green-500" :to="{ name: 'event-list-view' }">Event</RouterLink>
          <RouterLink class="font-bold text-gray-700" exact-active-class="text-green-500" :to="{ name: 'about' }">About</RouterLink>
          <RouterLink class="font-bold text-gray-700" exact-active-class="text-green-500" :to="{ name: 'student' }">Student</RouterLink>
        </nav>
      </div>
    </header>
    <RouterView :key="$route.fullPath" />
  </div>
</template>

<style> 
/* #layout {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
} */
/* nav {
  padding: 30px;
}
nav a {
  font-weight: bold;
  color: #2c3e50;
}
nav a.router-link-exact-active {
  color: #42b983;
}
.pagination-controls {
  margin: 20px;
}
.pagination-controls button {
  margin: 0 10px;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  background: linear-gradient(145deg, #6ac1ff, #3d8eff);
  color: white;
  font-weight: bold;
  cursor: pointer;
  transition: background 0.3s, transform 0.3s;
  box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.1);
}
.pagination-controls button:hover {
  background: linear-gradient(145deg, #3d8eff, #6ac1ff);
  transform: translateY(-3px);
}
.pagination-controls button:active {
  background: linear-gradient(145deg, #3d8eff, #6ac1ff);
  transform: translateY(1px);
} */

@keyframes yellofade {
  from {
    background-color: yellow;
  }
  to {
    background-color: transparent;
  }
}
/* #flashMessage {
  animation: yellofade 3s ease-in-out;
} */
</style>
