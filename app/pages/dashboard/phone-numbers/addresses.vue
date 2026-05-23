<template>
  <DashboardLayout>
    <div class="p-24 w-full">
      <h1 class="text-4xl font-light text-gray-900 mb-12">
        {{ isAddingAddress ? 'New Address' : 'Addresses' }}
      </h1>

      <div v-if="!isAddingAddress" class="flex flex-col items-center justify-center pt-10 text-center">
        <div class="mb-8">
          <div class="w-24 h-24 bg-gray-100 rounded-full flex items-center justify-center border border-gray-200">
            <svg class="w-12 h-12 text-gray-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z" />
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
            </svg>
          </div>
        </div>

        <h2 class="text-2xl text-gray-800 mb-4">No addresses have been created.</h2>
        <p class="text-gray-400 max-w-lg mb-8 leading-relaxed">
          Addresses can be assigned to phone numbers on your account for uses like E911 or locality requirements for international phone numbers.
        </p>

        <button 
          @click="isAddingAddress = true"
          class="px-10 py-3 bg-blue-600 text-white font-semibold rounded-full hover:bg-blue-700 transition shadow-sm"
        >
          Add an address
        </button>
      </div>

      <div v-else class="space-y-10 pb-20">
        
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-start">
          <div class="pr-8">
            <h3 class="text-lg font-bold text-gray-900 mb-1">Country</h3>
            <p class="text-sm text-gray-500">Select the country for this address.</p>
          </div>
          <div class="space-y-1">
            <label class="text-xs font-bold text-gray-700 uppercase">Country</label>
            <select class="w-full px-4 py-2 bg-white border border-gray-300 rounded-lg outline-none focus:ring-2 focus:ring-blue-500">
              <option>🇺🇸 United States of America</option>
              <option>🇨🇦 Canada</option>
              <option>🇬🇧 United Kingdom</option>
            </select>
          </div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-start">
          <div class="pr-8">
            <h3 class="text-lg font-bold text-gray-900 mb-1">Name</h3>
            <p class="text-sm text-gray-500">Give this Address a name to easily find and search for it later.</p>
          </div>
          <div class="space-y-1">
            <label class="text-xs font-bold text-gray-700 uppercase">Label</label>
            <input type="text" class="w-full px-4 py-2 border border-gray-300 rounded-lg outline-none focus:ring-2 focus:ring-blue-500" />
          </div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-start">
          <div class="pr-8">
            <h3 class="text-lg font-bold text-gray-900 mb-1">Contact Name</h3>
            <p class="text-sm text-gray-500">The name associated with this address.</p>
          </div>
          <div class="grid grid-cols-2 gap-4">
            <div class="space-y-1">
              <label class="text-xs font-bold text-gray-700 uppercase">First Name</label>
              <input type="text" class="w-full px-4 py-2 border border-gray-300 rounded-lg outline-none focus:ring-2 focus:ring-blue-500" />
            </div>
            <div class="space-y-1">
              <label class="text-xs font-bold text-gray-700 uppercase">Last Name</label>
              <input type="text" class="w-full px-4 py-2 border border-gray-300 rounded-lg outline-none focus:ring-2 focus:ring-blue-500" />
            </div>
          </div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-start">
          <div class="pr-8">
            <h3 class="text-lg font-bold text-gray-900 mb-1">Street Address</h3>
            <p class="text-sm text-gray-500">The street number and name for this address.</p>
          </div>
          <div class="grid grid-cols-3 gap-4">
            <div class="space-y-1 col-span-1">
              <label class="text-xs font-bold text-gray-700 uppercase">Street Number</label>
              <input type="text" class="w-full px-4 py-2 border border-gray-300 rounded-lg outline-none focus:ring-2 focus:ring-blue-500" />
            </div>
            <div class="space-y-1 col-span-2">
              <label class="text-xs font-bold text-gray-700 uppercase">Street Name</label>
              <input type="text" class="w-full px-4 py-2 border border-gray-300 rounded-lg outline-none focus:ring-2 focus:ring-blue-500" />
            </div>
          </div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-start">
          <div class="pr-8">
            <h3 class="text-lg font-bold text-gray-900 mb-1">Apartment, Suite, Etc.</h3>
            <p class="text-sm text-gray-500">Add apartment, suite, building, floor, etc if applicable.</p>
          </div>
          <div class="grid grid-cols-2 gap-4">
            <div class="space-y-1">
              <label class="text-xs font-bold text-gray-700 uppercase">Address Type - <span class="italic font-normal capitalize">Optional</span></label>
              <select class="w-full px-4 py-2 bg-white border border-gray-300 rounded-lg outline-none focus:ring-2 focus:ring-blue-500">
                <option value="">-Select Type-</option>
                <option>Apartment</option>
                <option>Suite</option>
                <option>Building</option>
              </select>
            </div>
            <div class="space-y-1">
              <label class="text-xs font-bold text-gray-700 uppercase">Address Number - <span class="italic font-normal capitalize">Optional</span></label>
              <input type="text" class="w-full px-4 py-2 border border-gray-300 rounded-lg outline-none focus:ring-2 focus:ring-blue-500" />
            </div>
          </div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-start">
          <div class="pr-8">
            <h3 class="text-lg font-bold text-gray-900 mb-1">City</h3>
            <p class="text-sm text-gray-500">The city for this address.</p>
          </div>
          <div class="space-y-1">
            <label class="text-xs font-bold text-gray-700 uppercase">City</label>
            <input type="text" class="w-full px-4 py-2 border border-gray-300 rounded-lg outline-none focus:ring-2 focus:ring-blue-500" />
          </div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-start">
          <div class="pr-8">
            <h3 class="text-lg font-bold text-gray-900 mb-1">State / Province</h3>
            <p class="text-sm text-gray-500">Select or enter the state or province for this address.</p>
          </div>
          <div class="space-y-1">
            <label class="text-xs font-bold text-gray-700 uppercase">State - <span class="italic font-normal capitalize">Optional</span></label>
            <select class="w-full px-4 py-2 bg-white border border-gray-300 rounded-lg outline-none focus:ring-2 focus:ring-blue-500">
              <option value="">-Select State-</option>
              <option>California</option>
              <option>New York</option>
              <option>Texas</option>
            </select>
          </div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-start">
          <div class="pr-8">
            <h3 class="text-lg font-bold text-gray-900 mb-1">Postal / ZIP Code</h3>
            <p class="text-sm text-gray-500">The postal or ZIP code for this address.</p>
          </div>
          <div class="space-y-1">
            <label class="text-xs font-bold text-gray-700 uppercase">Postal Code</label>
            <input type="text" class="w-full px-4 py-2 border border-gray-300 rounded-lg outline-none focus:ring-2 focus:ring-blue-500" />
          </div>
        </div>

        <div class="pt-8 border-t border-gray-100 flex gap-4">
          <button class="px-10 py-2.5 bg-blue-600 text-white font-bold rounded-full hover:bg-blue-700 transition shadow-md">
            Create
          </button>
          <button @click="isAddingAddress = false" class="px-8 py-2.5 text-gray-500 font-bold hover:text-gray-700 transition">
            Cancel
          </button>
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
import { ref } from 'vue'
import DashboardLayout from '@/components/dashboard/DashboardLayout.vue'

const isAddingAddress = ref(false)
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
input:focus, select:focus {
  background-color: white;
}
</style>