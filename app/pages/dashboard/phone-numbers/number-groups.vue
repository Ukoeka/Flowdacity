<template>
  <DashboardLayout>
    <div class="p-12 w-full ">
      <h1 class="text-4xl font-light text-gray-900 mb-12">
        {{ isCreating ? 'New Number Group' : 'Number Groups' }}
      </h1>

      <div v-if="!isCreating" class="flex flex-col items-center justify-center pt-10 text-center">
        <div class="mb-8">
          <div class="w-24 h-24 bg-gray-100 rounded-full flex items-center justify-center border border-gray-200">
            <svg class="w-12 h-12 text-gray-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7" />
            </svg>
          </div>
        </div>

        <h2 class="text-2xl text-gray-800 mb-4">No Number Groups Setup</h2>
        <p class="text-gray-400 max-w-lg mb-8 leading-relaxed">
          Number Groups can be used for many things, like creating a pool of numbers used for sending text messages or setting up white- or black-lists to control call flow.
        </p>

        <button 
          @click="isCreating = true"
          class="px-10 py-3 bg-blue-600 text-white font-semibold rounded-full hover:bg-blue-700 transition shadow-sm"
        >
          Create a Number Group
        </button>
      </div>

      <div v-else class="w-full space-y-12">
        
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-start">
          <div class="pr-8">
            <h3 class="text-lg font-bold text-gray-900 mb-2">Name</h3>
            <p class="text-sm text-gray-500 leading-relaxed">
              Give this Number Group a friendly name to more easily find and search for it later.
            </p>
          </div>
          <div class="space-y-1">
            <label class="text-xs font-bold text-gray-700 uppercase tracking-wider">Name</label>
            <input 
              v-model="form.name"
              type="text" 
              class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 outline-none transition-all"
            />
          </div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-start">
          <div class="pr-8">
            <h3 class="text-lg font-bold text-gray-900 mb-2">Sticky Sender</h3>
            <p class="text-sm text-gray-500 leading-relaxed">
              When active, uses the same "From" number each time you contact a recipient.
            </p>
          </div>
          <div class="space-y-2">
            <label class="text-xs font-bold text-gray-700 uppercase tracking-wider block mb-2">Sticky Sender</label>
            <div class="flex items-center gap-3">
              <span class="text-sm font-medium" :class="!form.stickySender ? 'text-gray-900' : 'text-gray-400'">No</span>
              <button 
                @click="form.stickySender = !form.stickySender"
                class="relative inline-flex h-6 w-11 items-center rounded-full transition-colors focus:outline-none"
                :class="form.stickySender ? 'bg-blue-600' : 'bg-gray-200'"
              >
                <span 
                  :class="form.stickySender ? 'translate-x-6' : 'translate-x-1'"
                  class="inline-block h-4 w-4 transform rounded-full bg-white transition-transform"
                />
              </button>
              <span class="text-sm font-medium" :class="form.stickySender ? 'text-gray-900' : 'text-gray-400'">Yes</span>
            </div>
          </div>
        </div>

        <div class="pt-8 border-t border-gray-100">
          <h3 class="text-xl font-bold text-gray-900 mb-4">Phone Numbers</h3>
          <p class="text-gray-500 mb-8 leading-relaxed">
            No Phone Numbers yet.<br />
            Once you add phone numbers to your project, you will be able to add them to a group here.
          </p>

          <div class="flex gap-4">
            <button 
              class="px-10 py-2.5 bg-blue-600 text-white font-bold rounded-full hover:bg-blue-700 transition shadow-md"
            >
              Create
            </button>
            <button 
              @click="isCreating = false"
              class="px-8 py-2.5 text-gray-500 font-bold hover:text-gray-700 transition"
            >
              Cancel
            </button>
          </div>
        </div>
      </div>

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
            <div v-for="section in docs" :key="section.title" class="bg-white p-6 rounded-2xl border border-gray-100 shadow-lg hover:shadow-xl transition-shadow duration-300">
              <div class="flex items-center gap-3 mb-4">
                <span class="text-2xl">{{ section.icon }}</span>
                <h4 class="font-bold text-gray-900">{{ section.title }}</h4>
              </div>
              <ul class="space-y-3 text-sm">
                <li v-for="link in section.links" :key="link">
                  <a href="#" class="text-blue-600 hover:underline block">{{ link }}</a>
                </li>
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

const isCreating = ref(false)
const isDocsOpen = ref(true)

const form = reactive({
  name: '',
  stickySender: false
})

const docs = [
  {
    title: 'Guides',
    icon: '📋',
    links: ['Getting Started with Phone Numbers', 'Making and Receiving Phone Calls', 'Making and Receiving SMS']
  },
  {
    title: 'SDK Reference',
    icon: '💻',
    links: ['RELAY Realtime SDK', 'Compatibility SDK']
  },
  {
    title: 'REST API Reference',
    icon: '🔗',
    links: ['Phone Numbers', 'Number Groups']
  }
]
</script>

<style scoped>
.font-light {
  font-weight: 300;
}

/* Custom shadow for buttons to match Flowdacity style */
.shadow-md {
  shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
}
</style>