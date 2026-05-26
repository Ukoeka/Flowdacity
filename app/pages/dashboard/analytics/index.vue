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

    <!-- Footer -->
    <footer class="bg-gray-50 border-t border-gray-200 mt-8">
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
  </DashboardLayout>
</template>

<script setup>
import { ref } from 'vue'
import DashboardLayout from '../../../components/DashboardLayout.vue'

const selectedPeriod = ref('7days')
const showCustomDatePicker = ref(false)

const metrics = ref({
  totalCalls: '0',
  avgDuration: '0:00',
  avgMosScore: '0.0',
  callCompletion: '0%',
  qualityIssues: '0',
  avgPostDialDelay: '0.0s'
})

const getPeriodLabel = (period) => {
  switch (period) {
    case '7days':
      return 'Last 7 days'
    case '30days':
      return 'Last 30 days'
    case '90days':
      return 'Last 90 days'
    case 'custom':
      return 'Custom range'
    default:
      return 'Last 7 days'
  }
}
</script>

<style scoped>
.transition {
  transition-duration: 200ms;
}
</style>