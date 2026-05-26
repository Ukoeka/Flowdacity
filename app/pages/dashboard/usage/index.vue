<template>
  <DashboardLayout>
    <div class="p-8 w-full">
      <!-- Page Title -->
      <h1 class="text-4xl font-light text-gray-900 mb-8">Usage History</h1>

      <!-- Usage Table -->
      <div class="bg-white border border-gray-200 rounded-lg overflow-hidden">
        <div class="overflow-x-auto">
          <table class="w-full">
            <thead class="bg-gray-50 border-b border-gray-200">
              <tr>
                <th class="text-left px-6 py-4 text-sm font-semibold text-gray-900">Date</th>
                <th class="text-left px-6 py-4 text-sm font-semibold text-gray-900">Resource</th>
                <th class="text-left px-6 py-4 text-sm font-semibold text-gray-900">Charge</th>
                <th class="text-right px-6 py-4 text-sm font-semibold text-gray-900">Cost</th>
              </tr>
            </thead>
            <tbody>
              <tr
                v-for="transaction in transactions"
                :key="transaction.id"
                class="border-b border-gray-200 hover:bg-gray-50 transition"
              >
                <td class="px-6 py-4">
                  <p class="text-gray-900">{{ transaction.date }}</p>
                  <p class="text-sm text-gray-600">{{ transaction.time }}</p>
                </td>
                <td class="px-6 py-4">
                  <a href="#" class="text-blue-600 hover:text-blue-700 font-medium">{{ transaction.resource }}</a>
                  <p class="text-sm text-gray-600 mt-1">{{ transaction.resourceId }}</p>
                </td>
                <td class="px-6 py-4">
                  <p class="text-gray-900">{{ transaction.charge }}</p>
                </td>
                <td class="text-right px-6 py-4">
                  <p class="text-gray-900 font-semibold">{{ transaction.cost }}</p>
                </td>
              </tr>
            </tbody>
          </table>
        </div>

        <!-- Empty State (if no transactions) -->
        <div v-if="transactions.length === 0" class="p-12 text-center">
          <svg class="w-16 h-16 text-gray-300 mx-auto mb-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z" />
          </svg>
          <h3 class="text-lg font-semibold text-gray-900 mb-2">No usage history</h3>
          <p class="text-gray-600">Your usage transactions will appear here</p>
        </div>
      </div>
    </div>

   
  </DashboardLayout>
</template>

<script setup>
import { ref } from 'vue'
import DashboardLayout from '@/components/dashboard/DashboardLayout.vue'

const transactions = ref([
  {
    id: 1,
    date: 'Jan 31, 2026',
    time: 'at 8:40PM UTC',
    resource: 'Tax Record',
    resourceId: '57c9caf9-c0c7-4751-be69-02683dda7c1',
    charge: 'Taxes/Surcharges',
    cost: '$0.123675'
  },
  {
    id: 2,
    date: 'Jan 7, 2026',
    time: 'at 6:31PM UTC',
    resource: 'Phone Number',
    resourceId: 'cfbc3cd5-b423-403b-8f0c-b696569abcaf',
    charge: 'Longcode Number (USA) Monthly Cost',
    cost: '$0.500000'
  },
  {
    id: 3,
    date: 'Dec 31, 2025',
    time: 'at 7:51PM UTC',
    resource: 'Tax Record',
    resourceId: '65145638-1bd8-4f37-b29f-cbfb97d7df0',
    charge: 'Taxes/Surcharges',
    cost: '$0.125297'
  },
  {
    id: 4,
    date: 'Dec 7, 2025',
    time: 'at 6:28PM UTC',
    resource: 'Phone Number',
    resourceId: 'cfbc3cd5-b423-403b-8f0c-b696569abcaf',
    charge: 'Longcode Number (USA) Monthly Cost',
    cost: '$0.500000'
  }
])
</script>

<style scoped>
.transition {
  transition-duration: 200ms;
}
</style>