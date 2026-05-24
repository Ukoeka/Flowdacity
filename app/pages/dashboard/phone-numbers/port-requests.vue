<template>
  <DashboardLayout>
    <div class="p-24 w-full  mx-auto">
      <h1 class="text-4xl font-light text-gray-900 mb-12">
        {{ isFormActive ? 'Submit a Port Request' : 'Port Requests' }}
      </h1>

      <div v-if="!isFormActive" class="flex flex-col items-center justify-center pt-10 text-center">
        <div class="mb-8">
          <div class="w-24 h-24 bg-gray-100 rounded-full flex items-center justify-center border border-gray-200">
            <svg class="w-16 h-16 text-gray-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M12 4v16m8-8H4m12.5 4.5L21 12m0 0l-4.5-4.5M21 12H9" />
            </svg>
          </div>
        </div>

        <h2 class="text-2xl text-gray-800 mb-4">Port Request Form</h2>
        <p class="text-gray-400 max-w-lg mb-8 leading-relaxed">
          Please submit your new port request using the form available within the Flowdacity Support Portal. 
          Click the button below to open the form.
        </p>

        <button 
          @click="isFormActive = true"
          class="px-10 py-3 bg-blue-600 text-white font-semibold rounded-full hover:bg-blue-700 transition shadow-sm"
        >
          Initiate Port Request
        </button>
      </div>

      <div v-else class="max-w-4xl mx-auto space-y-8">
        <div class="bg-white p-8 rounded-2xl border border-gray-200 shadow-sm space-y-6">
          <h2 class="text-2xl font-bold text-gray-900 border-b pb-4">Port In Request</h2>
          <p class="text-sm text-gray-500 italic">Please fill out this form to request porting your numbers to our service.</p>

          <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
            <div class="space-y-2">
              <label class="block text-sm font-bold text-gray-700">Contact Name <span class="text-red-500">*</span></label>
              <input type="text" class="w-full px-4 py-2 bg-gray-50 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 outline-none" />
              <p class="text-xs text-gray-400 italic">Authorized user requesting this port-in. Not for end-user info.</p>
            </div>

            <div class="space-y-2">
              <label class="block text-sm font-bold text-gray-700">Contact Email <span class="text-red-500">*</span></label>
              <input type="email" class="w-full px-4 py-2 bg-gray-50 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 outline-none" />
            </div>

            <div class="space-y-2 md:col-span-2">
              <label class="block text-sm font-bold text-gray-700">Project ID <span class="text-red-500">*</span></label>
              <input type="text" class="w-full px-4 py-2 bg-gray-50 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 outline-none" />
              <p class="text-xs text-gray-400">Copy and paste the Project ID where you want these numbers added.</p>
            </div>

            <div class="space-y-2 md:col-span-2">
              <label class="block text-sm font-bold text-gray-700">Numbers to Port <span class="text-red-500">*</span></label>
              <textarea rows="4" placeholder="One per line or separated by comma..." class="w-full px-4 py-2 bg-gray-50 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 outline-none"></textarea>
            </div>

            <div class="space-y-2 md:col-span-2">
              <label class="block text-sm font-bold text-gray-700">Services to Port <span class="text-red-500">*</span></label>
              <select class="w-full px-4 py-2 bg-gray-50 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 outline-none">
                <option value="">-Select Services-</option>
                <option value="voice_sms">Voice and Messaging</option>
                <option value="voice_only">Voice Only</option>
              </select>
              <div class="p-3 bg-orange-50 border-l-4 border-orange-400 text-xs text-orange-800 leading-relaxed">
                <strong>WARNING:</strong> TOLL-FREE NUMBERS DEFAULT TO VOICE ONLY UNLESS PROOF OF MESSAGING VERIFICATION IS PROVIDED.
              </div>
            </div>
          </div>
        </div>

        <div class="bg-white p-8 rounded-2xl border border-gray-200 shadow-sm space-y-6">
          <h3 class="text-xl font-bold text-gray-900 border-b pb-4">Current Provider Information</h3>
          
          <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
            <div class="space-y-2 md:col-span-2">
              <label class="block text-sm font-bold text-gray-700">10DLC Campaign ID <span class="text-red-500">*</span></label>
              <input type="text" placeholder="example: CXXXXXX" class="w-full px-4 py-2 bg-gray-50 border border-gray-300 rounded-lg outline-none focus:ring-2 focus:ring-blue-500" />
              <p class="text-xs text-gray-400 italic">For Messaging Services (If Applicable, otherwise type N/A)</p>
            </div>
            
            <div class="space-y-2">
              <label class="block text-sm font-bold text-gray-700">Current Provider Name <span class="text-red-500">*</span></label>
              <input type="text" class="w-full px-4 py-2 bg-gray-50 border border-gray-300 rounded-lg outline-none" />
            </div>

            <div class="space-y-2">
              <label class="block text-sm font-bold text-gray-700">Current Provider Account Number <span class="text-red-500">*</span></label>
              <input type="text" class="w-full px-4 py-2 bg-gray-50 border border-gray-300 rounded-lg outline-none" />
            </div>

            <div class="space-y-2 md:col-span-2">
              <label class="block text-sm font-bold text-gray-700">Account Type <span class="text-red-500">*</span></label>
              <select class="w-full px-4 py-2 bg-gray-50 border border-gray-300 rounded-lg outline-none">
                <option value="">-Select Account Type-</option>
                <option value="business">Business</option>
                <option value="individual">Individual</option>
              </select>
            </div>
          </div>
        </div>

        <div class="bg-white p-8 rounded-2xl border border-gray-200 shadow-sm space-y-6">
          <h3 class="text-xl font-bold text-gray-900 border-b pb-4">Letter of Authorization and Bill Copy</h3>
          
          <div class="space-y-4">
            <p class="text-sm text-gray-600">A signed LOA dated within the past 30 days is necessary. Please download and upload the form:</p>
            <div class="flex gap-4">
              <a href="#" class="text-blue-600 hover:underline text-sm font-medium flex items-center gap-1">📥 Toll-Free LOA Form</a>
              <a href="#" class="text-blue-600 hover:underline text-sm font-medium flex items-center gap-1">📥 Local TN LOA Form</a>
            </div>
            <div class="bg-yellow-50 p-3 rounded-lg border border-yellow-100 text-xs text-yellow-800">
              <strong>Note:</strong> To prevent unauthorized porting, we now require a recent bill copy along with your Letter of Authorization (LOA).
            </div>
          </div>

          <div class="space-y-2">
            <label class="block text-sm font-bold text-gray-700">Upload Files <span class="text-red-500">*</span></label>
            <div class="border-2 border-dashed border-gray-300 rounded-xl p-10 text-center hover:bg-gray-50 transition cursor-pointer">
              <div class="text-4xl mb-2 text-gray-300">+</div>
              <p class="text-sm font-bold text-blue-600">Upload files <span class="text-gray-500 font-normal text-xs">or drag and drop</span></p>
              <p class="text-xs text-gray-400 mt-1">PDF, DOC, DOCX, JPG, PNG up to 20MB per file</p>
            </div>
          </div>
        </div>

        <div class="flex justify-end gap-4 pb-12">
          <button @click="isFormActive = false" class="px-8 py-2.5 text-gray-600 font-bold hover:bg-gray-100 rounded-lg transition">Reset</button>
          <button class="px-10 py-2.5 bg-indigo-600 text-white font-bold rounded-lg hover:bg-indigo-700 transition shadow-md">Submit Request</button>
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
            <div v-for="section in docSections" :key="section.title" class="bg-white p-6 rounded-2xl border border-gray-100 shadow-lg">
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
import { ref } from 'vue'
import DashboardLayout from '@/components/dashboard/DashboardLayout.vue'

const isFormActive = ref(false)
const isDocsOpen = ref(true)

const docSections = [
  {
    title: 'Guides',
    emoji: '📋',
    links: ['Getting Started with Phone Numbers', 'Making and Receiving Phone Calls', 'Making and Receiving SMS']
  },
  {
    title: 'SDK Reference',
    emoji: '💻',
    links: ['RELAY Realtime SDK', 'Compatibility SDK']
  },
  {
    title: 'REST API Reference',
    emoji: '🔗',
    links: ['Phone Numbers', 'Number Groups']
  }
]
</script>

<style scoped>
.font-light { font-weight: 300; }
input:focus, textarea:focus, select:focus {
  border-color: #3b82f6;
  background-color: white;
}
</style>