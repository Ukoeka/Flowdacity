<template>
  <DashboardLayout>
    <div class="p-24 w-full">
      <!-- Page Title -->
      <h1 class="text-4xl font-light text-gray-900 mb-8">Purchased Numbers</h1>

      <!-- Search and Buy Section -->
      <div class="bg-gray-100 rounded-lg p-8 mb-8 flex items-center justify-between">
        <div class="flex-1">
          <input
            type="text"
            placeholder="Search by Name"
            class="w-full max-w-md px-4 py-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
          />
        </div>
        <button
          @click="showBuyModal = true"
          class="px-6 py-2 bg-blue-600 text-white font-semibold rounded-lg hover:bg-blue-700 transition"
        >
          + Buy
        </button>
      </div>

      <!-- Empty State -->
      <div class="bg-gray-100 rounded-lg  flex flex-col items-center  p-24 justify-center text-center mb-12">
        <div class="mb-6">
          <svg class="w-20 h-20 text-gray-400 mx-auto" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M8.25 3v1.5M4.5 8.25H3m18 0h-1.5M4.21 13.89a2.25 2.25 0 00-.2-.898l-.413-1.023a2.25 2.25 0 111.378-2.936l.58.581c.55.551.893 1.298.893 2.134 0 .377-.07.741-.205 1.08" />
          </svg>
        </div>
        <h2 class="text-2xl font-light text-gray-900 mb-3">Looks like there is nothing here!</h2>
        <p class="text-gray-600 max-w-md mb-6">
          Phone Numbers are the first step in sending and receiving calls, messages, faxes and more. Get your first number to get started!
        </p>
        <button
          @click="showBuyModal = true"
          class="px-6 py-3 bg-blue-600 text-white font-semibold rounded-lg hover:bg-blue-700 transition flex items-center gap-2"
        >
          <span>+</span> Buy A Number
        </button>
      </div>

      <p class="text-gray-600 mb-12">No Phone Numbers found</p>

      <!-- Developer Docs Section -->
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

    <!-- Buy A Number Modal -->
    <Teleport to="body">
      <transition
        enter-active-class="transition duration-200"
        enter-from-class="opacity-0"
        enter-to-class="opacity-100"
        leave-active-class="transition duration-200"
        leave-from-class="opacity-100"
        leave-to-class="opacity-0"
      >
        <div v-if="showBuyModal" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50">
          <!-- Modal Content -->
          <transition
            enter-active-class="transition duration-200"
            enter-from-class="opacity-0 scale-95"
            enter-to-class="opacity-100 scale-100"
            leave-active-class="transition duration-200"
            leave-from-class="opacity-100 scale-100"
            leave-to-class="opacity-0 scale-95"
          >
            <div v-if="showBuyModal" class="bg-white rounded-lg shadow-xl max-w-5xl w-full mx-4 max-h-[90vh] overflow-y-auto">
              <!-- Modal Header -->
              <div class="sticky top-0 bg-white border-b border-gray-200 px-8 py-6 flex items-center justify-between">
                <h2 class="text-2xl font-bold text-gray-900">Buy A Number</h2>
                <button
                  @click="showBuyModal = false"
                  class="text-gray-500 hover:text-gray-700"
                >
                  <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                  </svg>
                </button>
              </div>

              <!-- Modal Body -->
              <div class="p-8">
                <!-- Number Type Selection -->
                <div class="grid grid-cols-1 md:grid-cols-3 gap-4 mb-8">
                  <button
                    @click="selectedNumberType = 'local'"
                    :class="[
                      'p-6 rounded-lg border-2 transition text-center',
                      selectedNumberType === 'local'
                        ? 'border-blue-600 bg-blue-50'
                        : 'border-gray-200 hover:border-gray-300'
                    ]"
                  >
                    <div class="text-4xl mb-2">📞</div>
                    <h3 class="text-lg font-bold text-blue-600 mb-2">Local</h3>
                    <p class="text-sm text-gray-600">Local voice, fax, and application messaging services</p>
                  </button>

                  <button
                    @click="selectedNumberType = 'tollfree'"
                    :class="[
                      'p-6 rounded-lg border-2 transition text-center',
                      selectedNumberType === 'tollfree'
                        ? 'border-blue-600 bg-blue-50'
                        : 'border-gray-200 hover:border-gray-300'
                    ]"
                  >
                    <div class="text-4xl mb-2">☎️</div>
                    <h3 class="text-lg font-bold text-gray-900 mb-2">Toll Free</h3>
                    <p class="text-sm text-gray-600">Business voice, fax, and application messaging services</p>
                  </button>

                  <button
                    @click="selectedNumberType = 'shortcode'"
                    :class="[
                      'p-6 rounded-lg border-2 transition text-center',
                      selectedNumberType === 'shortcode'
                        ? 'border-blue-600 bg-blue-50'
                        : 'border-gray-200 hover:border-gray-300'
                    ]"
                  >
                    <div class="text-4xl mb-2">💬</div>
                    <h3 class="text-lg font-bold text-gray-900 mb-2">Shortcode</h3>
                    <p class="text-sm text-gray-600">Enterprise messaging and exclusive ownership</p>
                  </button>
                </div>

                <!-- Search Filters -->
                <div class="bg-gray-50 p-6 rounded-lg mb-8">
                  <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <div>
                      <label class="block text-sm font-semibold text-gray-900 mb-2">Search For Numbers - Optional</label>
                      <div class="flex">
                        <select class="flex-1 px-3 py-2 border border-gray-300 rounded-l-lg bg-white text-gray-700 focus:outline-none">
                          <option>Containing</option>
                        </select>
                        <input
                          type="text"
                          placeholder="Search"
                          class="flex-1 px-3 py-2 border border-l-0 border-gray-300 rounded-r-lg focus:outline-none"
                        />
                      </div>
                    </div>
                    <div>
                      <label class="block text-sm font-semibold text-gray-900 mb-2">Number Or Word - Optional</label>
                      <input
                        type="text"
                        placeholder="Any"
                        class="w-full px-3 py-2 border border-gray-300 rounded-lg focus:outline-none"
                      />
                    </div>
                  </div>

                  <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mt-4">
                    <div>
                      <label class="block text-sm font-semibold text-gray-900 mb-2">Area Code - Optional</label>
                      <input
                        type="text"
                        placeholder="Any"
                        class="w-full px-3 py-2 border border-gray-300 rounded-lg focus:outline-none"
                      />
                    </div>
                    <div>
                      <label class="block text-sm font-semibold text-gray-900 mb-2">Region - Optional</label>
                      <select class="w-full px-3 py-2 border border-gray-300 rounded-lg bg-white text-gray-700 focus:outline-none">
                        <option>Any</option>
                      </select>
                    </div>
                  </div>

                  <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mt-4">
                    <div>
                      <label class="block text-sm font-semibold text-gray-900 mb-2">City - Optional</label>
                      <input
                        type="text"
                        placeholder="Any"
                        class="w-full px-3 py-2 border border-gray-300 rounded-lg focus:outline-none"
                      />
                    </div>
                    <div>
                      <button class="w-full mt-6 px-6 py-2 bg-blue-600 text-white font-semibold rounded-lg hover:bg-blue-700 transition">
                        Search
                      </button>
                    </div>
                  </div>
                </div>

                <!-- Numbers Table -->
                <div class="overflow-x-auto">
                  <table class="w-full">
                    <thead>
                      <tr class="border-b border-gray-200">
                        <th class="text-left px-4 py-3 text-sm font-semibold text-gray-900">Number</th>
                        <th class="text-left px-4 py-3 text-sm font-semibold text-gray-900">Capabilities</th>
                        <th class="text-right px-4 py-3 text-sm font-semibold text-gray-900">Cost</th>
                        <th class="text-right px-4 py-3 text-sm font-semibold text-gray-900"></th>
                      </tr>
                    </thead>
                    <tbody>
                      <tr v-for="(number, idx) in availableNumbers" :key="idx" class="border-b border-gray-200 hover:bg-gray-50">
                        <td class="px-4 py-3">
                          <p class="font-semibold text-gray-900">{{ number.phone }}</p>
                          <p class="text-sm text-gray-600">{{ number.location }}</p>
                        </td>
                        <td class="px-4 py-3">
                          <div class="flex gap-2">
                            <span v-if="number.capabilities.voice" class="text-lg">📞</span>
                            <span v-if="number.capabilities.sms" class="text-lg">💬</span>
                            <span v-if="number.capabilities.fax" class="text-lg">📄</span>
                            <span v-if="number.capabilities.app" class="text-lg">📱</span>
                          </div>
                        </td>
                        <td class="text-right px-4 py-3 text-gray-900 font-semibold">{{ number.cost }}</td>
                        <td class="text-right px-4 py-3">
                          <button class="px-4 py-1 border-2 border-blue-600 text-blue-600 font-semibold rounded hover:bg-blue-50 transition">
                            Buy
                          </button>
                        </td>
                      </tr>
                    </tbody>
                  </table>
                </div>
              </div>
            </div>
          </transition>
        </div>
      </transition>
    </Teleport>

    <!-- Footer -->
    
  </DashboardLayout>
</template>

<script setup>
import { ref } from 'vue'
import DashboardLayout from '@/components/dashboard/DashboardLayout.vue'

const showBuyModal = ref(false)
const selectedNumberType = ref('local')
const isDocsOpen = ref(true)

const availableNumbers = ref([
  {
    phone: '+1 (201) 979-7916',
    location: 'New Jersey',
    capabilities: { voice: true, sms: true, fax: true, app: true },
    cost: '$0.50 / month'
  },
  {
    phone: '+1 (201) 979-7956',
    location: 'New Jersey',
    capabilities: { voice: true, sms: true, fax: true, app: true },
    cost: '$0.50 / month'
  },
  {
    phone: '+1 (201) 979-7986',
    location: 'New Jersey',
    capabilities: { voice: true, sms: true, fax: true, app: true },
    cost: '$0.50 / month'
  },
  {
    phone: '+1 (201) 979-8015',
    location: 'New Jersey',
    capabilities: { voice: true, sms: true, fax: true, app: true },
    cost: '$0.50 / month'
  },
  {
    phone: '+1 (201) 979-8019',
    location: 'New Jersey',
    capabilities: { voice: true, sms: true, fax: true, app: true },
    cost: '$0.50 / month'
  },
])
</script>

<style scoped>
.transition {
  transition-duration: 200ms;
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