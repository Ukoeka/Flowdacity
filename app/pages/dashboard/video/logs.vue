<template>
  <DashboardLayout>
    <div class="p-24 w-full">
      <!-- Page Title -->
      <h1 class="text-4xl font-light text-gray-900 mb-16">Video Logs</h1>

      <!-- Empty State -->
      <div class="flex flex-col items-center justify-center py-20">
        <!-- Icon -->
        <div class="mb-6">
          <svg class="w-24 h-24 text-gray-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M9 19V6l12-3v13M9 19c0 1.105-1.343 2-3 2s-3-.895-3-2 1.343-2 3-2 3 .895 3 2zm12-3c0 1.105-1.343 2-3 2s-3-.895-3-2 1.343-2 3-2 3 .895 3 2zM9 10l12-3" />
          </svg>
        </div>

        <!-- Message -->
        <h2 class="text-2xl font-light text-gray-900 mb-3">Waiting for your first video...</h2>
        
        <!-- Description -->
        <p class="text-gray-600 text-center max-w-md mb-2">
          Learn more about getting started with Video on our
          <a href="#" class="text-blue-600 hover:text-blue-700 font-medium">Video Dashboard</a>,
          or jump right into creating a
          <a href="#" class="text-blue-600 hover:text-blue-700 font-medium">Video Conference Room</a>
          with the click of a button.
        </p>
      </div>

      <!-- Developer Docs Section -->
      <div class="mt-24 pt-8 border-t border-gray-100">
        <div class="flex items-center gap-4 mb-8">
          <button 
            @click="isDocsOpen = !isDocsOpen"
            class="flex items-center gap-2 bg-gray-50 border border-gray-200 px-4 py-1.5 rounded-lg text-gray-700 font-bold text-sm hover:bg-gray-100 transition shadow-sm group"
          >
            Developer Docs 
            <span :class="['text-blue-600 transition-transform duration-300 text-lg', isDocsOpen ? 'rotate-90' : '']">›</span>
          </button>
          
          <button class="text-blue-600 text-sm font-medium flex items-center gap-1 hover:underline">
             <span class="text-lg">❓</span> Help
          </button>
        </div>

        <transition
          enter-active-class="transition-all duration-300 ease-out"
          leave-active-class="transition-all duration-200 ease-in"
          enter-from-class="opacity-0 -translate-y-4 max-h-0"
          enter-to-class="opacity-100 translate-y-0 max-h-[1000px]"
          leave-from-class="opacity-100 translate-y-0 max-h-[1000px]"
          leave-to-class="opacity-0 -translate-y-4 max-h-0"
        >
          <div v-if="isDocsOpen" class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <div class="bg-white p-6 rounded-2xl border border-gray-100 shadow-lg hover:shadow-xl transition-shadow duration-300">
              <div class="flex items-center gap-3 mb-4">
                <span class="text-2xl">📋</span>
                <h4 class="font-bold text-gray-900">Guides</h4>
              </div>
              <ul class="space-y-3 text-sm">
                <li><a href="#" class="text-blue-600 hover:underline block">Integrate Video Conferences with any Website</a></li>
                <li><a href="#" class="text-blue-600 hover:underline block">First Steps with Video</a></li>
              </ul>
            </div>

            <div class="bg-white p-6 rounded-2xl border border-gray-100 shadow-lg hover:shadow-xl transition-shadow duration-300">
              <div class="flex items-center gap-3 mb-4">
                <span class="text-2xl">💻</span>
                <h4 class="font-bold text-gray-900">SDK Reference</h4>
              </div>
              <ul class="space-y-3 text-sm">
                <li><a href="#" class="text-blue-600 hover:underline block">RELAY Realtime SDK</a></li>
                <li><a href="#" class="text-blue-600 hover:underline block">RELAY Browser SDK</a></li>
              </ul>
            </div>

            <div class="bg-white p-6 rounded-2xl border border-gray-100 shadow-lg hover:shadow-xl transition-shadow duration-300">
              <div class="flex items-center gap-3 mb-4">
                <span class="text-2xl">🔗</span>
                <h4 class="font-bold text-gray-900">REST API Reference</h4>
              </div>
              <ul class="space-y-3 text-sm">
                <li><a href="#" class="text-blue-600 hover:underline block">Video Conferences</a></li>
                <li><a href="#" class="text-blue-600 hover:underline block">Room Tokens</a></li>
              </ul>
            </div>
          </div>
        </transition>
      </div>
    </div>

   
  </DashboardLayout>
</template>

<script setup>
import { ref } from 'vue'
import DashboardLayout from '@/components/dashboard/DashboardLayout.vue'

const isDocsOpen = ref(true)
</script>

<style scoped>
.transition {
  transition-duration: 200ms;
}

/* Transition styles for docs toggle */
.max-h-0 {
  max-height: 0;
  overflow: hidden;
}
.max-h-\[1000px\] {
  max-height: 1000px;
}
</style>