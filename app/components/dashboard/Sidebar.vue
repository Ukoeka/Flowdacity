<template>
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
      <NavItem 
        v-for="(item, index) in navigationItems" 
        :key="index"
        :icon="item.icon" 
        :label="item.label" 
        :active="item.active"
        @click="setActive(index)"
      />
    </nav>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import NavItem from '@/components/dashboard/NavItem.vue'

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
</style>