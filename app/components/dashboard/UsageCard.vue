<template>
  <div class="bg-white border border-gray-200 rounded-lg p-6 hover:shadow-lg transition">
    <!-- Header -->
    <div class="flex items-center gap-3 mb-6">
      <span class="text-3xl">{{ icon }}</span>
      <h3 class="text-base font-bold text-gray-900">{{ title }}</h3>
    </div>

    <!-- Metrics -->
    <div class="mb-6 space-y-4">
      <div>
        <p class="text-gray-500 font-semibold uppercase text-xs tracking-wide mb-1">Minutes</p>
        <p class="text-3xl font-bold text-gray-900">{{ minutes }}</p>
      </div>
      <div>
        <p class="text-gray-500 font-semibold uppercase text-xs tracking-wide mb-1">Cost</p>
        <p class="text-2xl font-bold text-gray-900">{{ cost }}</p>
      </div>
    </div>

    <!-- Chart Area -->
    <div class="mb-6 bg-gray-50 rounded-lg p-4 h-40 flex flex-col justify-end">
      <!-- Y-axis labels -->
      <div class="flex">
        <div class="w-12 text-right pr-2 space-y-8 text-xs text-gray-400 flex flex-col justify-end h-32">
          <span>0.6</span>
          <span>0.4</span>
          <span>0.2</span>
          <span>0</span>
        </div>
        
        <!-- Chart bars -->
        <div class="flex-1 flex items-end justify-between gap-3 h-32">
          <div class="flex-1 bg-gray-200 rounded-sm opacity-30 hover:opacity-50 transition"></div>
          <div class="flex-1 bg-gray-200 rounded-sm opacity-30 hover:opacity-50 transition"></div>
          <div class="flex-1 bg-gray-200 rounded-sm opacity-30 hover:opacity-50 transition"></div>
          <div class="flex-1 bg-gray-200 rounded-sm opacity-30 hover:opacity-50 transition"></div>
          <div class="flex-1 bg-gray-200 rounded-sm opacity-30 hover:opacity-50 transition"></div>
          <div class="flex-1 bg-gray-200 rounded-sm opacity-30 hover:opacity-50 transition"></div>
          <div class="flex-1 bg-gray-200 rounded-sm opacity-30 hover:opacity-50 transition"></div>
        </div>
      </div>

      <!-- X-axis -->
      <div class="flex mt-2 ml-14">
        <div class="flex-1"></div>
        <span class="text-xs text-gray-400 flex-1">May 13</span>
        <span class="text-xs text-gray-400 flex-1">May 15</span>
        <span class="text-xs text-gray-400 flex-1">May 17</span>
        <span class="text-xs text-gray-400 flex-1 text-right">May 19</span>
      </div>

      <!-- Price scale on right -->
      <div class="flex mt-4 ml-14">
        <div class="flex-1"></div>
        <div class="flex-1 flex flex-col justify-between h-20 text-xs text-gray-400">
          <span>$1</span>
          <span>$0.8</span>
          <span>$0.6</span>
          <span>$0.4</span>
          <span>$0.2</span>
          <span>$0</span>
        </div>
      </div>
    </div>

    <!-- Legend -->
    <div class="flex items-center justify-start gap-6 text-xs mb-4">
      <div v-if="title === 'Voice'" class="flex items-center gap-2">
        <div class="w-2 h-2 rounded-full bg-teal-500"></div>
        <span class="text-gray-600">Inbound</span>
      </div>
      <div v-if="title === 'Voice'" class="flex items-center gap-2">
        <div class="w-2 h-2 rounded-full bg-yellow-500"></div>
        <span class="text-gray-600">Outbound</span>
      </div>
      <div v-if="title === 'Video'" class="flex items-center gap-2">
        <div class="w-2 h-2 rounded-full bg-teal-500"></div>
        <span class="text-gray-600">720p</span>
      </div>
      <div v-if="title === 'Video'" class="flex items-center gap-2">
        <div class="w-2 h-2 rounded-full bg-yellow-500"></div>
        <span class="text-gray-600">1080p</span>
      </div>
      <div v-if="title === 'Messaging'" class="flex items-center gap-2">
        <div class="w-2 h-2 rounded-full bg-teal-500"></div>
        <span class="text-gray-600">SMS</span>
      </div>
      <div v-if="title === 'Messaging'" class="flex items-center gap-2">
        <div class="w-2 h-2 rounded-full bg-yellow-500"></div>
        <span class="text-gray-600">MMS</span>
      </div>
      <div class="flex items-center gap-2">
        <div class="w-2 h-2 rounded-full bg-gray-900"></div>
        <span class="text-gray-600">Cost</span>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  icon: String,
  minutes: String,
  cost: String,
})
</script>

<style scoped>
.transition {
  transition-duration: 200ms;
}
</style>