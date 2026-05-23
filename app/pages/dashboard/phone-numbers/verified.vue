<template>
  <DashboardLayout>
    <div class="p-24 w-full">
      <h1 class="text-3xl font-light text-gray-900 mb-8">
        {{ isVerifying ? 'Verify a Phone Number' : 'Verified Caller ID' }}
      </h1>

      <div v-if="!isVerifying && !hasVerifiedNumbers" class="flex flex-col items-center justify-center pt-20">
        <div class="mb-6 relative">
          <div class="w-24 h-24 rounded-full border-4 border-gray-200 flex items-center justify-center">
             <svg class="w-12 h-12 text-gray-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z" />
            </svg>
          </div>
        </div>
        
        <h2 class="text-2xl font-medium text-gray-800 mb-4">No Verified Caller IDs</h2>
        <p class="text-gray-500 text-center max-w-lg mb-8 leading-relaxed">
          Verified Caller IDs are numbers you have verified you own and allow you to make outbound calls from these numbers, in addition to numbers you've purchased.
        </p>

        <button 
          @click="isVerifying = true"
          class="px-8 py-3 bg-blue-600 text-white font-semibold rounded-full hover:bg-blue-700 transition-colors shadow-sm"
        >
          Verify a Phone Number
        </button>
      </div>

      <div v-if="isVerifying" class="max-w-4xl">
        <p class="text-gray-600 mb-4">
          Adding a phone number as a verified caller ID will allow you to send outgoing calls using this number as the caller ID.
        </p>
        <p class="text-gray-600 mb-10">
          Enter your phone number and we will call you with a verification code.
        </p>

        <div class="space-y-10">
          <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-start">
            <div>
              <h3 class="font-bold text-gray-800 mb-1">Phone Number</h3>
              <p class="text-sm text-gray-500">Enter the number you would like to verify, including the country code.</p>
            </div>
            <div class="space-y-1">
              <label class="text-sm font-medium text-gray-700">Number</label>
              <input 
                v-model="form.number"
                type="text" 
                placeholder="ex. 1 (555) 123-4567"
                class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 outline-none"
              />
            </div>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-start">
            <div>
              <h3 class="font-bold text-gray-800 mb-1">Extension</h3>
              <p class="text-sm text-gray-500">If the number you are dialing is behind an IVR or extension.</p>
            </div>
            <div class="space-y-1">
              <label class="text-sm font-medium text-gray-700 italic">Extension - <span class="text-gray-400">Optional</span></label>
              <input 
                v-model="form.extension"
                type="text" 
                class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 outline-none"
              />
              <p class="text-xs text-blue-600 cursor-pointer hover:underline">Learn more about extensions..</p>
            </div>
          </div>
        </div>

        <div class="mt-12">
          <button 
            @click="handleCallMe"
            class="px-10 py-3 bg-blue-600 text-white font-semibold rounded-full hover:bg-blue-700 transition-colors"
          >
            Call Me
          </button>
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
            <div class="bg-white p-6 rounded-2xl border border-gray-100 shadow-lg hover:shadow-xl transition-shadow duration-300">
              <div class="flex items-center gap-3 mb-4">
                <span class="text-2xl">📋</span>
                <h4 class="font-bold text-gray-900">Guides</h4>
              </div>
              <ul class="space-y-3 text-sm">
                <li><a href="#" class="text-blue-600 hover:underline block">Getting Started with Phone Numbers</a></li>
                <li><a href="#" class="text-blue-600 hover:underline block">Making and Receiving Phone Calls</a></li>
                <li><a href="#" class="text-blue-600 hover:underline block">Making and Receiving SMS</a></li>
              </ul>
            </div>

            <div class="bg-white p-6 rounded-2xl border border-gray-100 shadow-lg hover:shadow-xl transition-shadow duration-300">
              <div class="flex items-center gap-3 mb-4">
                <span class="text-2xl">💻</span>
                <h4 class="font-bold text-gray-900">SDK Reference</h4>
              </div>
              <ul class="space-y-3 text-sm">
                <li><a href="#" class="text-blue-600 hover:underline block">RELAY Realtime SDK</a></li>
                <li><a href="#" class="text-blue-600 hover:underline block">Compatibility SDK</a></li>
              </ul>
            </div>

            <div class="bg-white p-6 rounded-2xl border border-gray-100 shadow-lg hover:shadow-xl transition-shadow duration-300">
              <div class="flex items-center gap-3 mb-4">
                <span class="text-2xl">🔗</span>
                <h4 class="font-bold text-gray-900">REST API Reference</h4>
              </div>
              <ul class="space-y-3 text-sm">
                <li><a href="#" class="text-blue-600 hover:underline block">Phone Numbers</a></li>
                <li><a href="#" class="text-blue-600 hover:underline block">Number Groups</a></li>
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

const isVerifying = ref(false)
const hasVerifiedNumbers = ref(false)
const isDocsOpen = ref(true)

const form = reactive({
  number: '',
  extension: ''
})

const handleCallMe = () => {
  console.log('Initiating verification for:', form.number)
}
</script>

<style scoped>
.font-light {
  font-weight: 300;
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