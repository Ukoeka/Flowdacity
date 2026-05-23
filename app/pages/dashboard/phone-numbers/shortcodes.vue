<template>
  <DashboardLayout>
    <div class="p-24 w-full">
      <h1 class="text-4xl font-light text-gray-900 mb-12">Short Codes</h1>

      <div v-if="!isApplying" class="flex flex-col items-center justify-center pt-10 text-center">
        <div class="mb-8">
          <div class="w-24 h-24 bg-gray-100 rounded-full flex items-center justify-center overflow-hidden border border-gray-200">
            <svg class="w-16 h-16 text-gray-400 translate-y-2" fill="currentColor" viewBox="0 0 24 24">
              <path d="M12 4C6.48 4 2 8.48 2 14c0 5.52 4.48 10 10 10s10-4.48 10-10c0-5.52-4.48-10-10-10zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8zm-1-13h2v5h-2zm0 6h2v2h-2z" />
            </svg>
          </div>
        </div>

        <h2 class="text-2xl text-gray-800 mb-4">Take Messaging to the Next Level</h2>
        <p class="text-gray-400 max-w-lg mb-8 leading-relaxed">
          Short Codes offer unparalleled messaging throughput and deliverability. They are the best choice for messaging heavy applications!
        </p>

        <button 
          @click="isApplying = true"
          class="px-10 py-3 bg-blue-600 text-white font-semibold rounded-full hover:bg-blue-700 transition shadow-sm"
        >
          Get a Short Code
        </button>
      </div>

      <div v-else class="flex flex-col items-center max-w-3xl mx-auto pt-4 text-center">
        <div class="mb-6 text-gray-300">
          <svg class="w-20 h-20 mx-auto" fill="currentColor" viewBox="0 0 24 24">
            <path d="M20 2H4c-1.1 0-2 .9-2 2v18l4-4h14c1.1 0 2-.9 2-2V4c0-1.1-.9-2-2-2z" />
          </svg>
        </div>

        <h2 class="text-2xl text-gray-800 mb-6">Short Code Application Process</h2>
        
        <div class="text-gray-600 space-y-6 text-left">
          <p>
            The Short Code Application process takes approximately five (5) to seven (7) weeks to complete. 
            SignalWire's acceptance of a Short Code Application as complete does not guarantee carrier approval. 
            SignalWire's carriers have the sole authority to approve or reject any Short Code Application.
          </p>

          <div class="bg-blue-50 p-6 rounded-xl border border-blue-100">
            <p class="mb-3 font-semibold text-blue-900">The following costs are associated with US short codes:</p>
            <ul class="list-disc ml-6 space-y-2 text-blue-800">
              <li>$750 account set-up fee (one-time passthrough charge from the carrier)</li>
              <li>Quarterly short code charge ($3,000 for vanity short codes; $1,500 for random short codes)</li>
              <li>$500 minimum spend per month (excluding taxes, fees, and quarterly short code charges)</li>
            </ul>
          </div>

          <p>
            Before submitting your Short Code registration request, we recommend you review and understand the following documentation first.
          </p>

          <ul class="space-y-2">
            <li>
              <a href="#" class="text-blue-600 hover:underline flex items-center gap-1">
                <span class="text-xs">▶</span> CTIA Best Practice Guidelines (PDF)
              </a>
            </li>
            <li>
              <a href="#" class="text-blue-600 hover:underline flex items-center gap-1">
                <span class="text-xs">▶</span> CTIA Short Code Handbook (PDF)
              </a>
            </li>
          </ul>
        </div>

        <div class="mt-10 flex flex-col items-center gap-6">
          <label class="flex items-center gap-3 cursor-pointer group">
            <input 
              type="checkbox" 
              v-model="hasAgreed"
              class="w-5 h-5 rounded border-gray-300 text-blue-600 focus:ring-blue-500"
            />
            <span class="text-gray-700 group-hover:text-gray-900 transition">
              I have read and agree to the above terms
            </span>
          </label>

          <div class="flex gap-4">
            <button 
              @click="isApplying = false"
              class="px-8 py-3 text-gray-500 font-semibold hover:text-gray-700 transition"
            >
              Cancel
            </button>
            <button 
              :disabled="!hasAgreed"
              :class="[
                'px-10 py-3 font-semibold rounded-full transition-all',
                hasAgreed 
                  ? 'bg-blue-600 text-white hover:bg-blue-700 shadow-md' 
                  : 'bg-gray-200 text-gray-400 cursor-not-allowed'
              ]"
            >
              Apply for a Short Code
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
import { ref } from 'vue'
import DashboardLayout from '@/components/dashboard/DashboardLayout.vue'


const isApplying = ref(false)
const hasAgreed = ref(false)
const isDocsOpen = ref(true) 
</script>

<style scoped>
.max-h-0 {
  max-height: 0;
  overflow: hidden;
}
.max-h-\[1000px\] {
  max-height: 1000px;
}
.font-light {
  font-weight: 300;
}
</style>