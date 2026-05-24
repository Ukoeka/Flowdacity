<template>
  <DashboardLayout>
    <div class="p-24 w-full">
      <!-- Charts Section -->
      <div class="mb-12">
        <div class="grid grid-cols-1 lg:grid-cols-3 gap-8 mb-8">
          <!-- Voice Chart -->
          <UsageCard 
            title="Voice"
            icon="🎤"
            value="0"
            cost="$0.00"
          />

          <!-- Video Chart -->
          <UsageCard 
            title="Video"
            icon="📹"
            value="0"
            cost="$0.00"
          />

          <!-- Messaging Chart -->
          <UsageCard 
            title="Messaging"
            icon="💬"
            value="0"
            cost="$0.00"
          />
        </div>
      </div>

      <!-- Shortcuts -->
      <div class="mb-12">
        <h2 class="text-lg font-bold text-gray-900 mb-6">Shortcuts</h2>

        <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
          <!-- Phone Numbers -->
          <div class="bg-white border border-gray-200 rounded-lg p-6 hover:shadow-sm transition">
            <div class="flex items-center justify-between mb-6">
              <h3 class="text-base font-bold text-gray-900">Phone Numbers</h3>
              <button class="text-blue-600 hover:text-blue-700 font-semibold text-sm flex items-center gap-1">
                <span class="text-lg">⊞</span> New
              </button>
            </div>

            <div class="grid grid-cols-4 gap-4">
              <div class="text-center">
                <p class="text-2xl font-bold text-gray-900">0</p>
                <p class="text-xs text-gray-500 mt-1">Local</p>
              </div>
              <div class="text-center">
                <p class="text-2xl font-bold text-gray-900">0</p>
                <p class="text-xs text-gray-500 mt-1">Toll Free</p>
              </div>
              <div class="text-center">
                <p class="text-2xl font-bold text-gray-900">0</p>
                <p class="text-xs text-gray-500 mt-1">Verified</p>
              </div>
              <div class="text-center">
                <p class="text-2xl font-bold text-gray-900">0</p>
                <p class="text-xs text-gray-500 mt-1">Short Code</p>
              </div>
            </div>
          </div>

          <!-- Video -->
          <div class="bg-white border border-gray-200 rounded-lg p-6 hover:shadow-sm transition">
            <div class="flex items-center justify-between mb-6">
              <h3 class="text-base font-bold text-gray-900">Video</h3>
              <button class="text-blue-600 hover:text-blue-700 font-semibold text-sm flex items-center gap-1">
                <span class="text-lg">⊞</span> New
              </button>
            </div>

            <div class="grid grid-cols-5 gap-4">
              <div class="text-center">
                <p class="text-2xl font-bold text-gray-900">0</p>
                <p class="text-xs text-gray-500 mt-1">Rooms</p>
              </div>
              <div class="text-center">
                <p class="text-2xl font-bold text-gray-900">0</p>
                <p class="text-xs text-gray-500 mt-1">In Progress</p>
              </div>
              <div class="text-center">
                <p class="text-2xl font-bold text-gray-900">0</p>
                <p class="text-xs text-gray-500 mt-1">Sessions</p>
              </div>
              <div class="text-center">
                <p class="text-2xl font-bold text-gray-900">0</p>
                <p class="text-xs text-gray-500 mt-1">Recordings</p>
              </div>
              <div></div>
            </div>
          </div>
        </div>
      </div>

      <!-- Build It Up Section -->
      <div class="mb-12">
        <h2 class="text-sm font-bold text-gray-900 uppercase tracking-wide mb-8">Build It Up</h2>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <!-- Card 1 -->
          <div class="bg-white border border-gray-200 rounded-lg p-6 hover:shadow-lg transition">
            <h3 class="text-blue-600 font-bold text-base mb-2">Flowdacity Tutorials & Guides</h3>
            <p class="text-gray-600 text-sm leading-relaxed">
              A collection of how-tos and resources to get you up and running on Flowdacity quickly and easily.
            </p>
          </div>

          <!-- Card 2 -->
          <div class="bg-white border border-gray-200 rounded-lg p-6 hover:shadow-lg transition">
            <h3 class="text-blue-600 font-bold text-base mb-2">Add a Number</h3>
            <p class="text-gray-600 text-sm leading-relaxed">
              Add multiple phone numbers to your project and have each interact with different configurations.
            </p>
          </div>

          <!-- Card 3 -->
          <div class="bg-white border border-gray-200 rounded-lg p-6 hover:shadow-lg transition">
            <h3 class="text-blue-600 font-bold text-base mb-2">Create an API Token</h3>
            <p class="text-gray-600 text-sm leading-relaxed">
              Create an API token to programmatically connect to Flowdacity and control your projects from your own servers.
            </p>
          </div>
        </div>
      </div>

      <!-- Learn More Section -->
      <div class="mb-12">
        <h2 class="text-sm font-bold text-gray-900 uppercase tracking-wide mb-8">Learn More</h2>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <!-- Card 1 -->
          <div class="bg-white border border-gray-200 rounded-lg p-6 hover:shadow-lg transition">
            <h3 class="text-blue-600 font-bold text-base mb-2">API Documentation & Server Side SDKs</h3>
            <p class="text-gray-600 text-sm leading-relaxed">
              Learn how to use Flowdacity's RELAY API and SDKs.
            </p>
          </div>

          <!-- Card 2 -->
          <div class="bg-white border border-gray-200 rounded-lg p-6 hover:shadow-lg transition">
            <h3 class="text-blue-600 font-bold text-base mb-2">Compatibility API Documentation</h3>
            <p class="text-gray-600 text-sm leading-relaxed">
              Learn how to use Flowdacity's Compatibility APIs.
            </p>
          </div>

          <!-- Card 3 -->
          <div class="bg-white border border-gray-200 rounded-lg p-6 hover:shadow-lg transition">
            <h3 class="text-blue-600 font-bold text-base mb-2">Get Some Support</h3>
            <p class="text-gray-600 text-sm leading-relaxed">
              Talk to our helpful community or support staff to quickly get answers to your questions.
            </p>
          </div>
        </div>
      </div>
    </div>

  </DashboardLayout>
</template>

<script setup>
import DashboardLayout from '@/components/dashboard/DashboardLayout.vue'
import UsageCard from '@/components/dashboard/UsageCard.vue'
</script>

<style scoped>
.transition {
  transition-duration: 200ms;
}
</style>