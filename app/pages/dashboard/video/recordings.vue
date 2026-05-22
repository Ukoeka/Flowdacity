<template>
  <DashboardLayout>
    <div class="p-8 w-full">
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
      <div class="mt-20">
        <div class="flex items-center gap-2 mb-8">
          <h3 class="text-lg font-bold text-gray-900">Developer Docs</h3>
          <button class="text-gray-400 hover:text-gray-600" title="More info">
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd" d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-7-4a1 1 0 11-2 0 1 1 0 012 0zM9 9a1 1 0 000 2v3a1 1 0 001 1h1a1 1 0 100-2v-3a1 1 0 00-1-1H9z" clip-rule="evenodd" />
            </svg>
          </button>
          <a href="#" class="text-blue-600 hover:text-blue-700 font-medium text-sm flex items-center gap-1 ml-auto">
            <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd" d="M18.5 5a1.5 1.5 0 11-3 0 1.5 1.5 0 013 0zm-1.5 3a2.5 2.5 0 11-5 0 2.5 2.5 0 015 0zm-6-1a1.5 1.5 0 11-3 0 1.5 1.5 0 013 0zm-.5 3a2.5 2.5 0 11-5 0 2.5 2.5 0 015 0z" clip-rule="evenodd" />
            </svg>
            Help
          </a>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <!-- Guides Card -->
          <div class="bg-white border border-gray-200 rounded-lg p-6 hover:shadow-lg transition">
            <div class="flex items-start gap-3 mb-4">
              <svg class="w-5 h-5 text-gray-700 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 20 20">
                <path d="M9 4.5a2.5 2.5 0 100 5 2.5 2.5 0 000-5zM5.5 9a4 4 0 118 0 4 4 0 01-8 0z" />
                <path d="M9 15c-3.5 0-6.5 1.5-6.5 3.5S5.5 22 9 22s6.5-1.5 6.5-3.5S12.5 15 9 15z" />
              </svg>
              <h4 class="font-bold text-gray-900">Guides</h4>
            </div>
            <ul class="space-y-2">
              <li>
                <a href="#" class="text-blue-600 hover:text-blue-700 text-sm font-medium">
                  Integrate Video Conferences with any Website
                </a>
              </li>
              <li>
                <a href="#" class="text-blue-600 hover:text-blue-700 text-sm font-medium">
                  First Steps with Video
                </a>
              </li>
            </ul>
          </div>

          <!-- SDK Reference Card -->
          <div class="bg-white border border-gray-200 rounded-lg p-6 hover:shadow-lg transition">
            <div class="flex items-start gap-3 mb-4">
              <svg class="w-5 h-5 text-gray-700 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 20 20">
                <path d="M12.316 3.051a1 1 0 01.633 1.265l-4 12a1 1 0 11-1.898-.633l4-12a1 1 0 011.265-.632zM5.707 6.293a1 1 0 010 1.414L3.414 10l2.293 2.293a1 1 0 11-1.414 1.414l-3-3a1 1 0 010-1.414l3-3a1 1 0 011.414 0zm8.586 0a1 1 0 011.414 0l3 3a1 1 0 010 1.414l-3 3a1 1 0 11-1.414-1.414L16.586 10l-2.293-2.293a1 1 0 010-1.414z" />
              </svg>
              <h4 class="font-bold text-gray-900">SDK Reference</h4>
            </div>
            <ul class="space-y-2">
              <li>
                <a href="#" class="text-blue-600 hover:text-blue-700 text-sm font-medium">
                  RELAY Realtime SDK
                </a>
              </li>
              <li>
                <a href="#" class="text-blue-600 hover:text-blue-700 text-sm font-medium">
                  RELAY Browser SDK
                </a>
              </li>
            </ul>
          </div>

          <!-- REST API Reference Card -->
          <div class="bg-white border border-gray-200 rounded-lg p-6 hover:shadow-lg transition">
            <div class="flex items-start gap-3 mb-4">
              <svg class="w-5 h-5 text-gray-700 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 20 20">
                <path d="M3 4a1 1 0 011-1h12a1 1 0 011 1v2a1 1 0 01-1 1H4a1 1 0 01-1-1V4zM3 10a1 1 0 011-1h12a1 1 0 011 1v6a1 1 0 01-1 1H4a1 1 0 01-1-1v-6z" />
              </svg>
              <h4 class="font-bold text-gray-900">REST API Reference</h4>
            </div>
            <ul class="space-y-2">
              <li>
                <a href="#" class="text-blue-600 hover:text-blue-700 text-sm font-medium">
                  Video Conferences
                </a>
              </li>
              <li>
                <a href="#" class="text-blue-600 hover:text-blue-700 text-sm font-medium">
                  Room Tokens
                </a>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>

    
  </DashboardLayout>
</template>

<script setup>
import DashboardLayout from '@/components/dashboard/DashboardLayout.vue'
</script>

<style scoped>
.transition {
  transition-duration: 200ms;
}
</style>