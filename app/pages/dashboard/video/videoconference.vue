<template>
  <DashboardLayout>
    <div class="p-8 w-full">
      <!-- Page Title -->
      <h1 class="text-4xl font-light text-gray-900 mb-16">Video Conferences</h1>

      <!-- Empty State -->
      <div class="flex flex-col items-center justify-center py-32">
        <!-- Icon -->
        <div class="mb-8">
          <svg class="w-24 h-24 text-gray-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M15 10l4.553-2.276A1 1 0 0121 8.618v6.764a1 1 0 01-1.447.894L15 14M5 18h8a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v8a2 2 0 002 2z" />
          </svg>
        </div>

        <!-- Message -->
        <h2 class="text-2xl font-light text-gray-900 mb-6">Waiting for your close up...</h2>
        
        <!-- Description -->
        <p class="text-gray-600 text-center max-w-2xl mb-8">
          SignalWire Video Rooms allow you to take complete control of your video experience providing feature rich building blocks you can use to customize your application.
        </p>

        <p class="text-gray-600 text-center max-w-2xl mb-8">
          They can be used in any website or application and provide low-level control via our REST SDK and RealTime APIs, giving you all the events and control to built anything you can imagine.
        </p>

        <!-- CTA Button -->
        <button class="px-8 py-3 bg-blue-600 text-white font-semibold rounded-full hover:bg-blue-700 transition">
          Create an API Room
        </button>
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

    <!-- Footer -->
    <footer class="bg-gray-50 border-t border-gray-200 mt-8">
      <div class="px-8 py-6 flex items-center justify-center gap-8 text-sm text-gray-600">
        <a href="#" class="hover:text-gray-900">About Us</a>
        <a href="#" class="hover:text-gray-900">API Docs</a>
        <a href="#" class="hover:text-gray-900">Guides</a>
        <a href="#" class="hover:text-gray-900">Legal</a>
        <a href="#" class="hover:text-gray-900">Privacy Policy</a>
        <a href="#" class="hover:text-gray-900">Terms of Use</a>
        <a href="#" class="hover:text-gray-900">Cookie Policy</a>
      </div>
    </footer>
  </DashboardLayout>
</template>

<script setup>
import DashboardLayout from '../../../components/DashboardLayout.vue'
</script>

<style scoped>
.transition {
  transition-duration: 200ms;
}
</style>