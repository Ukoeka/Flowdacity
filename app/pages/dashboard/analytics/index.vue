<template>
  <DashboardLayout>
    <div class="p-8 w-full">
      <!-- Header Section -->
      <div class="flex items-center justify-between mb-8">
        <h1 class="text-4xl font-light text-gray-900">Voice Analytics Dashboard</h1>
        <div class="flex gap-3">
          <button
            @click="selectedPeriod = '7days'"
            :class="[
              'px-4 py-2 font-semibold rounded-lg transition',
              selectedPeriod === '7days'
                ? 'bg-blue-600 text-white'
                : 'bg-gray-100 text-gray-700 hover:bg-gray-200'
            ]"
          >
            Last 7 Days
          </button>
          <button
            @click="selectedPeriod = '30days'"
            :class="[
              'px-4 py-2 font-semibold rounded-lg transition',
              selectedPeriod === '30days'
                ? 'bg-blue-600 text-white'
                : 'bg-gray-100 text-gray-700 hover:bg-gray-200'
            ]"
          >
            Last 30 Days
          </button>
          <button
            @click="selectedPeriod = '90days'"
            :class="[
              'px-4 py-2 font-semibold rounded-lg transition',
              selectedPeriod === '90days'
                ? 'bg-blue-600 text-white'
                : 'bg-gray-100 text-gray-700 hover:bg-gray-200'
            ]"
          >
            Last 90 Days
          </button>
          <button
            @click="showCustomDatePicker = !showCustomDatePicker"
            :class="[
              'px-4 py-2 font-semibold rounded-lg transition flex items-center gap-2',
              selectedPeriod === 'custom'
                ? 'bg-blue-600 text-white'
                : 'bg-gray-100 text-gray-700 hover:bg-gray-200'
            ]"
          >
            <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 20 20">
              <path d="M5.5 13a3 3 0 0 1 3-3h4a3 3 0 0 1 3 3v2.5M3 8h14M5 3h10a2 2 0 0 1 2 2v10a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2z" />
            </svg>
            Custom
          </button>
        </div>
      </div>

      <!-- Key Metrics Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 mb-8">
        <!-- Total Calls -->
        <div class="bg-white border border-gray-200 rounded-lg p-6">
          <h3 class="text-sm font-semibold text-gray-600 uppercase tracking-wide mb-2">Total Calls</h3>
          <p class="text-4xl font-bold text-gray-900 mb-2">{{ metrics.totalCalls }}</p>
          <p class="text-sm text-gray-600">{{ getPeriodLabel(selectedPeriod) }}</p>
        </div>

        <!-- Avg Duration -->
        <div class="bg-white border border-gray-200 rounded-lg p-6">
          <h3 class="text-sm font-semibold text-gray-600 uppercase tracking-wide mb-2">Avg Duration</h3>
          <p class="text-4xl font-bold text-gray-900 mb-2">{{ metrics.avgDuration }}</p>
          <p class="text-sm text-gray-600">Minutes</p>
        </div>

        <!-- AVG MOS Score -->
        <div class="bg-white border border-gray-200 rounded-lg p-6">
          <h3 class="text-sm font-semibold text-gray-600 uppercase tracking-wide mb-2">AVG MOS Score</h3>
          <p class="text-4xl font-bold text-gray-900 mb-2">{{ metrics.avgMosScore }}</p>
          <p class="text-sm text-gray-600">Quality</p>
        </div>

        <!-- Call Completion ASR -->
        <div class="bg-white border border-gray-200 rounded-lg p-6">
          <h3 class="text-sm font-semibold text-gray-600 uppercase tracking-wide mb-2">Call Completion (ASR)</h3>
          <p class="text-4xl font-bold text-gray-900 mb-2">{{ metrics.callCompletion }}</p>
          <p class="text-sm text-gray-600">Answer Seizure Ratio</p>
        </div>

        <!-- Quality Issues -->
        <div class="bg-white border border-gray-200 rounded-lg p-6">
          <h3 class="text-sm font-semibold text-gray-600 uppercase tracking-wide mb-2">Quality Issues</h3>
          <p class="text-4xl font-bold text-gray-900 mb-2">{{ metrics.qualityIssues }}</p>
          <p class="text-sm text-gray-600">Calls</p>
        </div>

        <!-- Avg Post-Dial Delay -->
        <div class="bg-white border border-gray-200 rounded-lg p-6">
          <h3 class="text-sm font-semibold text-gray-600 uppercase tracking-wide mb-2">Avg Post-Dial Delay</h3>
          <p class="text-4xl font-bold text-gray-900 mb-2">{{ metrics.avgPostDialDelay }}</p>
          <p class="text-sm text-gray-600">Time to Answer</p>
        </div>
      </div>

      <!-- Call Volume Chart -->
      <div class="bg-white border border-gray-200 rounded-lg p-6 mb-8">
        <h2 class="text-2xl font-bold text-gray-900 mb-6">Call Volume ({{ getPeriodLabel(selectedPeriod) }})</h2>
        <div class="h-80 flex items-center justify-center">
          <p class="text-gray-500">No call volume data available</p>
        </div>
      </div>

      <!-- Call Quality Distribution and Hangup Analysis -->
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 mb-8">
        <!-- Call Quality Distribution -->
        <div class="bg-white border border-gray-200 rounded-lg p-6">
          <h2 class="text-2xl font-bold text-gray-900 mb-6">Call Quality Distribution (MOS Score)</h2>
          <div class="h-64 flex items-center justify-center">
            <p class="text-gray-500">No quality data available</p>
          </div>
        </div>

        <!-- Hangup Analysis -->
        <div class="bg-white border border-gray-200 rounded-lg p-6">
          <h2 class="text-2xl font-bold text-gray-900 mb-6">Hangup Analysis</h2>
          <div class="h-64 flex items-center justify-center">
            <p class="text-gray-500">No hangup data available</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Custom Date Range Modal -->
    <Teleport to="body">
      <transition
        enter-active-class="transition duration-200"
        enter-from-class="opacity-0"
        enter-to-class="opacity-100"
        leave-active-class="transition duration-200"
        leave-from-class="opacity-100"
        leave-to-class="opacity-0"
      >
        <div v-if="showCustomDatePicker" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 p-4">
          <transition
            enter-active-class="transition duration-200"
            enter-from-class="opacity-0 scale-95"
            enter-to-class="opacity-100 scale-100"
            leave-active-class="transition duration-200"
            leave-from-class="opacity-100 scale-100"
            leave-to-class="opacity-0 scale-95"
          >
            <div v-if="showCustomDatePicker" class="bg-white rounded-lg shadow-xl w-full max-w-md">
              <!-- Modal Header -->
              <div class="border-b border-gray-200 px-6 py-4">
                <h2 class="text-xl font-bold text-gray-900">Select Custom Date Range</h2>
              </div>

              <!-- Modal Body -->
              <div class="p-6 space-y-6">
                <!-- Start Date -->
                <div>
                  <label class="block text-sm font-semibold text-gray-900 mb-2">Start Date</label>
                  <div class="relative">
                    <input
                      v-model="customDateRange.startDate"
                      type="date"
                      class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
                    />
                  </div>
                </div>

                <!-- End Date -->
                <div>
                  <label class="block text-sm font-semibold text-gray-900 mb-2">End Date</label>
                  <div class="relative">
                    <input
                      v-model="customDateRange.endDate"
                      type="date"
                      class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
                    />
                  </div>
                </div>

                <!-- Buttons -->
                <div class="space-y-3 pt-4 border-t border-gray-200">
                  <button
                    @click="applyCustomDateRange"
                    class="w-full px-6 py-3 bg-blue-600 text-white font-semibold rounded-full hover:bg-blue-700 transition"
                  >
                    Apply Date Range
                  </button>
                  <button
                    @click="cancelCustomDateRange"
                    class="w-full px-6 py-3 border-2 border-gray-300 text-gray-900 font-semibold rounded-full hover:bg-gray-50 transition"
                  >
                    Cancel
                  </button>
                </div>
              </div>
            </div>
          </transition>
        </div>
      </transition>
    </Teleport>

   
  </DashboardLayout>
</template>

<script setup>
import { ref, computed } from 'vue'
import DashboardLayout from '@/components/dashboard/DashboardLayout.vue'

const selectedPeriod = ref('7days')
const showCustomDatePicker = ref(false)

const customDateRange = ref({
  startDate: '',
  endDate: ''
})

const metrics = ref({
  totalCalls: '0',
  avgDuration: '0:00',
  avgMosScore: '0.0',
  callCompletion: '0%',
  qualityIssues: '0',
  avgPostDialDelay: '0.0s'
})

const formatDate = (dateString) => {
  if (!dateString) return ''
  const date = new Date(dateString)
  return date.toLocaleDateString('en-US', { month: '2-digit', day: '2-digit', year: 'numeric' })
}

const getPeriodLabel = (period) => {
  switch (period) {
    case '7days':
      return 'Last 7 days'
    case '30days':
      return 'Last 30 days'
    case '90days':
      return 'Last 90 days'
    case 'custom':
      return `${formatDate(customDateRange.value.startDate)} to ${formatDate(customDateRange.value.endDate)}`
    default:
      return 'Last 7 days'
  }
}

const initializeDateRange = () => {
  // Set default dates (last 90 days)
  const endDate = new Date()
  const startDate = new Date()
  startDate.setDate(startDate.getDate() - 90)

  customDateRange.value.startDate = startDate.toISOString().split('T')[0]
  customDateRange.value.endDate = endDate.toISOString().split('T')[0]
}

const applyCustomDateRange = () => {
  if (customDateRange.value.startDate && customDateRange.value.endDate) {
    selectedPeriod.value = 'custom'
    showCustomDatePicker.value = false
    // Trigger data refresh with new date range
    // refreshAnalyticsData()
  }
}

const cancelCustomDateRange = () => {
  showCustomDatePicker.value = false
}

// Initialize date range on component mount
initializeDateRange()
</script>

<style scoped>
.transition {
  transition-duration: 200ms;
}
</style>