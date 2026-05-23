
<template>
  <DashboardLayout>
    <div class="p-8 w-full max-w-6xl mx-auto">
      <h1 class="text-4xl font-light text-gray-900 mb-8">Video Conferences</h1>

      <div v-if="!isCreating" class="flex items-center gap-8 border-b border-gray-200 mb-8">
        <button 
          v-for="tab in ['API Rooms', 'Prebuilt', 'Recordings']" 
          :key="tab"
          @click="currentTab = tab"
          :class="[
            'pb-4 text-sm font-bold transition-colors relative',
            currentTab === tab ? 'text-blue-600' : 'text-gray-500 hover:text-gray-700'
          ]"
        >
          {{ tab }}
          <div v-if="currentTab === tab" class="absolute bottom-0 left-0 w-full h-0.5 bg-blue-600"></div>
        </button>
      </div>

      <div v-if="!isCreating" class="flex flex-col items-center justify-center py-16 text-center">
        <div class="mb-8">
          <svg class="w-24 h-24 text-gray-200" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M15 10l4.553-2.276A1 1 0 0121 8.618v6.764a1 1 0 01-1.447.894L15 14M5 18h8a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v8a2 2 0 002 2z" />
          </svg>
        </div>

        <h2 class="text-2xl font-light text-gray-900 mb-6">
          {{ currentTab === 'API Rooms' ? 'Waiting for your close up...' : 'Nothing here yet' }}
        </h2>
        
        <p class="text-gray-500 max-w-2xl mb-4 leading-relaxed">
          Flowdacity Video Rooms allow you to take complete control of your video experience providing feature rich building blocks you can use to customize your application.
        </p>

        <p class="text-gray-500 max-w-2xl mb-12 leading-relaxed">
          They can be used in any website or application and provide low-level control via our REST SDK and RealTime APIs.
        </p>

        <button 
          @click="isCreating = true"
          class="px-10 py-3 bg-blue-600 text-white font-semibold rounded-full hover:bg-blue-700 transition shadow-md"
        >
          Create an API Room
        </button>
      </div>

      <div v-else class="max-w-4xl space-y-12 pb-20">
        <div class="flex items-center justify-between mb-8">
          <h2 class="text-2xl font-bold text-gray-900">New API Room</h2>
          <button @click="isCreating = false" class="text-gray-400 hover:text-gray-600">
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" /></svg>
          </button>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-start">
          <div>
            <h3 class="font-bold text-gray-900 mb-1">Name</h3>
            <p class="text-sm text-gray-500">The name for this Video Room.</p>
          </div>
          <div class="space-y-1">
            <label class="text-xs font-bold text-gray-700 uppercase">Name</label>
            <input type="text" placeholder="Friendly Name" class="w-full px-4 py-2 border border-gray-300 rounded-lg outline-none focus:ring-2 focus:ring-blue-500" />
          </div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-start">
          <div>
            <h3 class="font-bold text-gray-900 mb-1">Room Layout</h3>
            <p class="text-sm text-gray-500">Determine how you would like the layout to appear for all users.</p>
          </div>
          <div class="space-y-1">
            <label class="text-xs font-bold text-gray-700 uppercase">Layout</label>
            <select class="w-full px-4 py-2 bg-white border border-gray-300 rounded-lg outline-none focus:ring-2 focus:ring-blue-500">
              <option>grid</option>
              <option>1x1</option>
              <option>2x2</option>
            </select>
          </div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-start">
          <div>
            <h3 class="font-bold text-gray-900 mb-1">Quality</h3>
            <p class="text-sm text-gray-500">The video quality for this room.</p>
          </div>
          <div class="space-y-1">
            <label class="text-xs font-bold text-gray-700 uppercase">Quality</label>
            <select class="w-full px-4 py-2 bg-white border border-gray-300 rounded-lg outline-none focus:ring-2 focus:ring-blue-500">
              <option>720p</option>
              <option>1080p</option>
              <option>480p</option>
            </select>
          </div>
        </div>

        <div class="space-y-10">
          <div v-for="toggle in toggles" :key="toggle.title" class="grid grid-cols-1 md:grid-cols-2 gap-8 items-start">
            <div>
              <h3 class="font-bold text-gray-900 mb-1">{{ toggle.title }}</h3>
              <p class="text-sm text-gray-500">{{ toggle.desc }}</p>
            </div>
            <div class="flex items-center gap-3">
              <span class="text-sm font-medium" :class="!toggle.value ? 'text-gray-900' : 'text-gray-400'">No</span>
              <button 
                @click="toggle.value = !toggle.value"
                class="relative inline-flex h-6 w-11 items-center rounded-full transition-colors"
                :class="toggle.value ? 'bg-blue-600' : 'bg-gray-200'"
              >
                <span :class="toggle.value ? 'translate-x-6' : 'translate-x-1'" class="inline-block h-4 w-4 transform rounded-full bg-white transition-transform" />
              </button>
              <span class="text-sm font-medium" :class="toggle.value ? 'text-gray-900' : 'text-gray-400'">Yes</span>
            </div>
          </div>
        </div>

        <div class="pt-8 border-t border-gray-100 flex gap-4">
          <button class="px-10 py-2.5 bg-blue-600 text-white font-bold rounded-full hover:bg-blue-700 transition shadow-md">Create</button>
          <button @click="isCreating = false" class="px-8 py-2.5 text-gray-500 font-bold hover:text-gray-700 transition">Cancel</button>
        </div>
      </div>

      <div class="mt-12 pt-8 border-t border-gray-100">
        <div class="flex items-center gap-4 mb-8">
          <button 
            @click="isDocsOpen = !isDocsOpen"
            class="flex items-center gap-2 bg-gray-50 border border-gray-200 px-4 py-1.5 rounded-lg text-gray-700 font-bold text-sm hover:bg-gray-100 transition shadow-sm"
          >
            Developer Docs 
            <span :class="['text-blue-600 transition-transform duration-300 text-lg', isDocsOpen ? 'rotate-90' : '']">›</span>
          </button>
          <button class="text-blue-600 text-sm font-medium hover:underline">❓ Help</button>
        </div>

        <transition
          enter-active-class="transition-all duration-300 ease-out"
          leave-active-class="transition-all duration-200 ease-in"
          enter-from-class="opacity-0 -translate-y-4 max-h-0"
          enter-to-class="opacity-100 translate-y-0 max-h-[1000px]"
          leave-from-class="opacity-100 translate-y-0 max-h-[1000px]"
          leave-to-class="opacity-0 -translate-y-4 max-h-0"
        >
          <div v-if="isDocsOpen" class="grid grid-cols-1 md:grid-cols-3 gap-8 pb-10">
            <div v-for="section in docSections" :key="section.title" class="bg-white p-6 rounded-2xl border border-gray-100 shadow-lg hover:shadow-xl transition-shadow duration-300">
              <div class="flex items-center gap-3 mb-4">
                <span class="text-2xl">{{ section.emoji }}</span>
                <h4 class="font-bold text-gray-900">{{ section.title }}</h4>
              </div>
              <ul class="space-y-3 text-sm">
                <li v-for="link in section.links" :key="link"><a href="#" class="text-blue-600 hover:underline block">{{ link }}</a></li>
              </ul>
            </div>
          </div>
        </transition>
      </div>
    </div>
  </DashboardLayout>
</template>

<script setup>
import { ref, reactive } from 'vue'
import DashboardLayout from '@/components/dashboard/DashboardLayout.vue'

const currentTab = ref('API Rooms')
const isCreating = ref(false)
const isDocsOpen = ref(true)

const toggles = reactive([
  { title: 'Record On Start', desc: 'When active, the room will be recorded once it starts.', value: false },
  { title: 'Hide Video Muted', desc: 'When active, muted participants are hidden from the layout.', value: false },
  { title: 'Lock Room', desc: 'When active, no new participants can join the room.', value: false }
])

const docSections = [
  { emoji: '📋', title: 'Guides', links: ['Integrate Video Conferences with any Website', 'First Steps with Video'] },
  { emoji: '💻', title: 'SDK Reference', links: ['RELAY Realtime SDK', 'RELAY Browser SDK'] },
  { emoji: '🔗', title: 'REST API Reference', links: ['Video Conferences', 'Room Tokens'] }
]
</script>

<style scoped>
.font-light { font-weight: 300; }
</style>