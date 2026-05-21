<template>
  <DashboardLayout>
    <div class="p-8 w-full">
          <!-- Charts Section -->
          <div class="mb-12">
             <div class="grid grid-cols-1 lg:grid-cols-3 gap-8 mb-8">
               <!-- Voice Chart -->
               <div class="bg-white border border-gray-200 rounded-lg p-6 hover:shadow-lg transition">
                 <!-- Header -->
                 <div class="flex items-center gap-3 mb-6">
                   <span class="text-3xl">🎤</span>
                   <h3 class="text-base font-bold text-gray-900">Voice</h3>
                 </div>
 
                 <!-- Metrics -->
                 <div class="mb-6 space-y-4">
                   <div>
                     <p class="text-gray-500 font-semibold uppercase text-xs tracking-wide mb-1">Minutes</p>
                     <p class="text-3xl font-bold text-gray-900">0</p>
                   </div>
                   <div>
                     <p class="text-gray-500 font-semibold uppercase text-xs tracking-wide mb-1">Cost</p>
                     <p class="text-2xl font-bold text-gray-900">$0.00</p>
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
                   <div class="flex items-center gap-2">
                     <div class="w-2 h-2 rounded-full bg-teal-500"></div>
                     <span class="text-gray-600">Inbound</span>
                   </div>
                   <div class="flex items-center gap-2">
                     <div class="w-2 h-2 rounded-full bg-yellow-500"></div>
                     <span class="text-gray-600">Outbound</span>
                   </div>
                   <div class="flex items-center gap-2">
                     <div class="w-2 h-2 rounded-full bg-gray-900"></div>
                     <span class="text-gray-600">Cost</span>
                   </div>
                 </div>
               </div>
 
               <!-- Video Chart -->
               <div class="bg-white border border-gray-200 rounded-lg p-6 hover:shadow-lg transition">
                 <!-- Header -->
                 <div class="flex items-center gap-3 mb-6">
                   <span class="text-3xl">📹</span>
                   <h3 class="text-base font-bold text-gray-900">Video</h3>
                 </div>
 
                 <!-- Metrics -->
                 <div class="mb-6 space-y-4">
                   <div>
                     <p class="text-gray-500 font-semibold uppercase text-xs tracking-wide mb-1">Minutes</p>
                     <p class="text-3xl font-bold text-gray-900">0</p>
                   </div>
                   <div>
                     <p class="text-gray-500 font-semibold uppercase text-xs tracking-wide mb-1">Cost</p>
                     <p class="text-2xl font-bold text-gray-900">$0.00</p>
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
                   <div class="flex items-center gap-2">
                     <div class="w-2 h-2 rounded-full bg-teal-500"></div>
                     <span class="text-gray-600">720p</span>
                   </div>
                   <div class="flex items-center gap-2">
                     <div class="w-2 h-2 rounded-full bg-yellow-500"></div>
                     <span class="text-gray-600">1080p</span>
                   </div>
                   <div class="flex items-center gap-2">
                     <div class="w-2 h-2 rounded-full bg-gray-900"></div>
                     <span class="text-gray-600">Cost</span>
                   </div>
                 </div>
               </div>
 
               <!-- Messaging Chart -->
               <div class="bg-white border border-gray-200 rounded-lg p-6 hover:shadow-lg transition">
                 <!-- Header -->
                 <div class="flex items-center gap-3 mb-6">
                   <span class="text-3xl">💬</span>
                   <h3 class="text-base font-bold text-gray-900">Messaging</h3>
                 </div>
 
                 <!-- Metrics -->
                 <div class="mb-6 space-y-4">
                   <div>
                     <p class="text-gray-500 font-semibold uppercase text-xs tracking-wide mb-1">Minutes</p>
                     <p class="text-3xl font-bold text-gray-900">0</p>
                   </div>
                   <div>
                     <p class="text-gray-500 font-semibold uppercase text-xs tracking-wide mb-1">Cost</p>
                     <p class="text-2xl font-bold text-gray-900">$0.00</p>
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
                   <div class="flex items-center gap-2">
                     <div class="w-2 h-2 rounded-full bg-teal-500"></div>
                     <span class="text-gray-600">SMS</span>
                   </div>
                   <div class="flex items-center gap-2">
                     <div class="w-2 h-2 rounded-full bg-yellow-500"></div>
                     <span class="text-gray-600">MMS</span>
                   </div>
                   <div class="flex items-center gap-2">
                     <div class="w-2 h-2 rounded-full bg-gray-900"></div>
                     <span class="text-gray-600">Cost</span>
                   </div>
                 </div>
               </div>
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
  </DashboardLayout>
</template>

<script setup>
import DashboardLayout from '@/components/dashboard/DashboardLayout.vue'
import ShortcutItem from '@/components/dashboard/ShortCut.vue'
</script>

<style scoped>
.transition {
  transition-duration: 200ms;
}
</style>