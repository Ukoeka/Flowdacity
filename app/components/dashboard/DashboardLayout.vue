<template>
  <div class="flex h-screen bg-gray-50">
    <!-- Sidebar -->
    <div class="w-64 bg-white border-r border-gray-200 overflow-y-auto fixed h-screen">
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
        <template v-for="(item, index) in navigationItems" :key="index">
           <!-- Item with subpages -->
           <div v-if="item.children">
             <div
               :class="[
                 'w-full flex items-center justify-between rounded-lg text-sm font-medium transition-colors',
                 isActiveGroup(item)
                   ? 'bg-gray-100 text-gray-900 border-l-4 border-purple-600'
                   : 'text-gray-600 hover:bg-gray-50 hover:text-gray-900'
               ]"
             >
               <NuxtLink
                 v-if="item.to"
                 :to="item.to"
                 class="flex items-center gap-3 px-3 py-2 flex-1"
               >
                 <span class="text-lg">{{ item.icon }}</span>
                 <span>{{ item.label }}</span>
               </NuxtLink>
                <div
                  v-else
                  class="flex items-center gap-3 px-3 py-2 flex-1 cursor-pointer"
                  @click="toggleSubmenu(index)"
                >
                  <span class="text-lg">{{ item.icon }}</span>
                  <span>{{ item.label }}</span>
                </div>
               <button
                 @click.stop="toggleSubmenu(index)"
                 class="px-2 py-2 hover:bg-gray-100 rounded-r-lg"
               >
                 <svg
                   :class="[
                     'w-4 h-4 transition-transform',
                     openSubmenus[index] ? 'rotate-180' : ''
                   ]"
                   fill="none"
                   stroke="currentColor"
                   viewBox="0 0 24 24"
                 >
                   <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3" />
                 </svg>
               </button>
             </div>

            <!-- Submenu items -->
            <transition
              enter-active-class="transition duration-200"
              enter-from-class="opacity-0 -translate-y-2"
              enter-to-class="opacity-100 translate-y-0"
              leave-active-class="transition duration-200"
              leave-from-class="opacity-100 translate-y-0"
              leave-to-class="opacity-0 -translate-y-2"
            >
              <div v-show="openSubmenus[index]" class="pl-8 space-y-1 bg-gray-50">
                <NuxtLink
                  v-for="(child, childIndex) in item.children"
                  :key="childIndex"
                  :to="child.to"
                  :class="[
                    'flex items-center gap-3 px-3 py-2 rounded-lg text-sm font-medium transition-colors',
                    route.path === child.to
                      ? 'bg-purple-50 text-purple-600 border-l-2 border-purple-600'
                      : 'text-gray-600 hover:bg-gray-100 hover:text-gray-900'
                  ]"
                >
                  <span>{{ child.label }}</span>
                </NuxtLink>
              </div>
            </transition>
          </div>

          <!-- Regular item without subpages -->
          <NuxtLink
            v-else
            :to="item.to"
            :class="[
              'w-full flex items-center gap-3 px-3 py-2 rounded-lg text-sm font-medium transition-colors',
              route.path === item.to
                ? 'bg-gray-100 text-gray-900 border-l-4 border-purple-600'
                : 'text-gray-600 hover:bg-gray-50 hover:text-gray-900'
            ]"
          >
            <span class="text-lg">{{ item.icon }}</span>
            <span>{{ item.label }}</span>
          </NuxtLink>
        </template>
      </nav>
    </div>

    <!-- Main Column -->
    <div class="ml-64 flex-1 flex flex-col">
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

      <!-- Footer -->
      <footer class="bg-gray-50 border-t border-gray-200">
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
    </div>
  </div>
</template>

<script setup>
import { useRoute } from 'vue-router'
import { ref, computed, watch } from 'vue'

const route = useRoute()
const openSubmenus = ref({})

const navigationItems = [
  { icon: '🏠', label: 'Home', to: '/dashboard/home' },
  {
    icon: '📹',
    label: 'Video',
    to: '/dashboard/video',
    children: [
      { label: 'Logs', to: '/dashboard/video/logs' },
      { label: 'Conferences', to: '/dashboard/video/conferences' },
      { label: 'Recordings', to: '/dashboard/video/recordings' },
    ]
  },
  { icon: '📱', 
  label: 'Phone Numbers', 
  to: '/dashboard/phone-numbers',
  children: [
    { label: 'Verified', to: '/dashboard/phone-numbers/verified' },
    { label: 'Short Codes', to: '/dashboard/phone-numbers/shortcodes' },
    { label: 'Port Requests', to: '/dashboard/phone-numbers/port-requests' },
    { label: 'Number Groups', to: '/dashboard/phone-numbers/number-groups' },
    { label: 'Addresses', to: '/dashboard/phone-numbers/addresses' },
  ]
 },
  {
    icon: '🔄',
    label: 'Relay / SWML',
    children: [
      { label: 'Overview', to: '/dashboard/relay/overview' },
      { label: 'Logs', to: '/dashboard/relay/logs' },
    ]
  },
  { icon: '☎️', label: 'SIP', to: '/dashboard/sip' },
  {
    icon: '💬',
    label: 'cXML / LaML',
    children: [
      { label: 'Overview', to: '/dashboard/cxml/overview' },
      { label: 'Logs', to: '/dashboard/cxml/logs' },
    ]
  },
  {
    icon: '📢',
    label: 'Messaging Campaigns',
    children: [
      { label: 'Campaigns', to: '/dashboard/messaging/campaigns' },
      { label: 'Templates', to: '/dashboard/messaging/templates' },
      { label: 'Logs', to: '/dashboard/messaging/logs' },
    ]
  },
  { icon: '🤖', label: 'AI Agents', to: '/dashboard/ai-agents' },
  { icon: '🔀', label: 'Dialogflow', to: '/dashboard/dialogflow' },
  { icon: '🔗', label: 'Integrations', to: '/dashboard/integrations' },
  { icon: '☁️', label: 'API', to: '/dashboard/api' },
  { icon: '📊', label: 'Usage', to: '/dashboard/usage' },
  { icon: '📞', label: 'Call Flow Builder', to: '/dashboard/call-flow' },
  { icon: '📈', label: 'Analytics', to: '/dashboard/analytics' },
  {
    icon: '📋',
    label: 'Logs',
    children: [
      { label: 'Call Logs', to: '/dashboard/logs/calls' },
      { label: 'SMS Logs', to: '/dashboard/logs/sms' },
      { label: 'API Logs', to: '/dashboard/logs/api' },
    ]
  },
  { icon: '💾', label: 'Storage', to: '/dashboard/storage' },
  { icon: '⚙️', label: 'Configuration', to: '/dashboard/configuration' },
  { icon: '🛠️', label: 'Tools', to: '/dashboard/tools' },
]

const toggleSubmenu = (index) => {
  openSubmenus.value[index] = !openSubmenus.value[index]
}

const isActiveGroup = (item) => {
  if (!item.children) return false
  const onParent = item.to && route.path === item.to
  const onChild = item.children.some(child => route.path === child.to)
  return onParent || onChild || !!openSubmenus.value[navigationItems.indexOf(item)]
}

// Auto-open submenu if current route is the parent or a child
const setupOpenSubmenus = () => {
  navigationItems.forEach((item, index) => {
    if (item.children) {
      const onParent = item.to && route.path === item.to
      const onChild = item.children.some(child => route.path === child.to)
      if (onParent || onChild) {
        openSubmenus.value[index] = true
      }
    }
  })
}

// Setup on mount and watch route changes
setupOpenSubmenus()

watch(() => route.path, () => {
  setupOpenSubmenus()
})
</script>

<style scoped>
button {
  transition-duration: 150ms;
}
</style>