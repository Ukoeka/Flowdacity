<template>
  <div class="flex h-screen bg-gray-50">
    <!-- Sidebar -->
    <Sidebar />

    <!-- Main Content -->
    <div class="ml-56 flex-1 flex flex-col">
      <!-- Top Bar -->
      <div class="bg-white border-b border-gray-200 px-8 py-4 flex items-center justify-between sticky top-0 z-10 h-16">
        <div class="flex items-center gap-3">
          <svg class="w-5 h-5 text-gray-400" fill="currentColor" viewBox="0 0 20 20">
            <path d="M5.5 13a3 3 0 0 0 1.6.8H8c.07 0 .14-.01.21-.03A1.01 1.01 0 0 0 9 13v-1H3v1c0 .55.448 1 1 1h1.5z" />
            <path d="M14 4c.55 0 1 .45 1 1v8c0 .55-.45 1-1 1h-1V5c0-.55.45-1 1-1zm-4 0c.55 0 1 .45 1 1v8c0 .55-.45 1-1 1H9V5c0-.55.45-1 1-1zm4 12H9v2h5v-2z" />
          </svg>
          <span class="text-gray-700 font-medium">Flowdacity</span>
        </div>
        <div class="flex items-center gap-6">
          <button class="text-gray-600 hover:text-gray-900 text-sm font-medium">Changelog</button>
          <button class="text-gray-600 hover:text-gray-900 text-sm font-medium">Support</button>
          <button class="text-gray-600 hover:text-gray-900 text-sm font-medium">Docs</button>
          <div class="w-8 h-8 rounded-full bg-gradient-to-br from-pink-400 to-purple-500"></div>
        </div>
      </div>

      <!-- Scrollable Content -->
      <div class="flex-1 overflow-y-auto">
        <div class="p-8 w-full">
          <!-- Charts Section -->
          <div class="mb-12">
            <div class="grid grid-cols-1 lg:grid-cols-3 gap-8 mb-8">
              <!-- Voice Chart -->
              <UsageCard 
                title="Voice" 
                icon="🎤"
                minutes="0"
                cost="$0.00"
              />

              <!-- Video Chart -->
              <UsageCard 
                title="Video" 
                icon="📹"
                minutes="0"
                cost="$0.00"
              />

              <!-- Messaging Chart -->
              <UsageCard 
                title="Messaging" 
                icon="💬"
                minutes="0"
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
                  <ShortcutItem label="Local" value="0" color="text-blue-600" />
                  <ShortcutItem label="Toll Free" value="0" color="text-blue-600" />
                  <ShortcutItem label="Verified" value="0" color="text-blue-600" />
                  <ShortcutItem label="Short Code" value="0" color="text-blue-600" />
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
                  <ShortcutItem label="Rooms" value="0" color="text-blue-600" />
                  <ShortcutItem label="In Progress" value="0" color="text-blue-600" />
                  <ShortcutItem label="Sessions" value="0" color="text-blue-600" />
                  <ShortcutItem label="Recordings" value="0" color="text-blue-600" />
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
                <h3 class="text-blue-600 font-bold text-base mb-2">SignalWire Tutorials & Guides</h3>
                <p class="text-gray-600 text-sm leading-relaxed">
                  A collection of how-tos and resources to get you up and running on SignalWire quickly and easily.
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
                  Create an API token to programmatically connect to SignalWire and control your projects from your own servers.
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
                  Learn how to use SignalWire's RELAY API and SDKs.
                </p>
              </div>

              <!-- Card 2 -->
              <div class="bg-white border border-gray-200 rounded-lg p-6 hover:shadow-lg transition">
                <h3 class="text-blue-600 font-bold text-base mb-2">Compatibility API Documentation</h3>
                <p class="text-gray-600 text-sm leading-relaxed">
                  Learn how to use SignalWire's Compatibility APIs.
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
      </div>
    </div>
  </div>
</template>

<script setup>
import Sidebar from '@/components/dashboard/Sidebar.vue'
// import NavItem from '@/components/dashboard/NavItem.vue'
import UsageCard from '@/components/dashboard/UsageCard.vue'
import ShortcutItem from '@/components/dashboard/ShortCut.vue'
</script>

<style scoped>
</style>