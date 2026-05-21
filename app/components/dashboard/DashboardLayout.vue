<template>
  <div class="flex h-screen bg-gray-50">
    <!-- Sidebar -->
    <div class="w-56 bg-white border-r border-gray-200 overflow-y-auto fixed h-screen">
      <!-- Logo -->
      <div class="p-6 border-b border-gray-200">
        <div class="flex items-center gap-2">
          <div class="w-8 h-8 bg-gradient-to-br from-blue-500 to-purple-600 rounded-lg flex items-center justify-center">
            <span class="text-white font-bold text-sm">⚡</span>
          </div>
          <span class="font-bold text-lg text-gray-900">Flowdacity</span>
        </div>
      </div>

      <!-- Navigation -->
      <nav class="p-4 space-y-1">
        <button
          v-for="(item, index) in navigationItems"
          :key="index"
          @click="setActive(index)"
          :class="[
            'w-full flex items-center gap-3 px-3 py-2 rounded-lg text-sm font-medium transition-colors',
            item.active
              ? 'bg-gray-100 text-gray-900 border-l-4 border-purple-600'
              : 'text-gray-600 hover:bg-gray-50 hover:text-gray-900'
          ]"
        >
          <span class="text-lg">{{ item.icon }}</span>
          <span>{{ item.label }}</span>
        </button>
      </nav>
    </div>

    <!-- Main Column -->
    <div class="ml-56 flex-1 flex flex-col">
      <!-- Top Bar -->
      <div class="bg-white border-b border-gray-200 px-8 py-4 flex items-center justify-between sticky top-0 z-10 h-20">
        <div class="flex items-center gap-3">
          <svg class="w-5 h-5 text-gray-400" fill="currentColor" viewBox="0 0 20 20">
            <path d="M5.5 13a3 3 0 0 0 1.6.8H8c.07 0 .14-.01.21-.03A1.01 1.01 0 0 0 9 13v-1H3v1c0 .55.448 1 1 1h1.5z" />
            <path d="M14 4c.55 0 1 .45 1 1v8c0 .55-.45 1-1 1h-1V5c0-.55.45-1 1-1zm-4 0c.55 0 1 .45 1 1v8c0 .55-.45 1-1 1H9V5c0-.55.45-1 1-1zm4 12H9v2h5v-2z" />
          </svg>
          <span class="text-gray-700 font-medium">Flowdacity</span>
        </div>
        <div class="flex items-center gap-6">
          <button class="text-gray-600 hover:text-gray-900 text-sm font-medium">Changelog</button>
          <button class="text-gray-600 hover:text-gray-900 text-sm font-medium">Support</button>
          <button class="text-gray-600 hover:text-gray-900 text-sm font-medium">Docs</button>
          <div class="w-8 h-8 rounded-full bg-gradient-to-br from-pink-400 to-purple-500"></div>
        </div>
      </div>

      <!-- Page Content Slot -->
      <div class="flex-1 overflow-y-auto">
        <slot />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const activeIndex = ref(0)

const navigationItems = ref([
  { icon: '🏠', label: 'Home', active: true },
  { icon: '📹', label: 'Video', active: false },
  { icon: '📱', label: 'Phone Numbers', active: false },
  { icon: '🔄', label: 'Relay / SWML', active: false },
  { icon: '☎️', label: 'SIP', active: false },
  { icon: '💬', label: 'cXML / LaML', active: false },
  { icon: '📢', label: 'Messaging Campaigns', active: false },
  { icon: '🤖', label: 'AI Agents', active: false },
  { icon: '🔀', label: 'Dialogflow', active: false },
  { icon: '🔗', label: 'Integrations', active: false },
  { icon: '☁️', label: 'API', active: false },
  { icon: '📊', label: 'Usage', active: false },
  { icon: '📞', label: 'Call Flow Builder', active: false },
  { icon: '📈', label: 'Analytics', active: false },
  { icon: '📋', label: 'Logs', active: false },
  { icon: '💾', label: 'Storage', active: false },
  { icon: '⚙️', label: 'Configuration', active: false },
  { icon: '🛠️', label: 'Tools', active: false },
])

const setActive = (index) => {
  navigationItems.value.forEach((item, i) => {
    item.active = i === index
  })
  activeIndex.value = index
}
</script>

<style scoped>
button {
  transition-duration: 150ms;
}
</style>
