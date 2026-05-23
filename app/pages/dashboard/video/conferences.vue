<template>
  <DashboardLayout>
    <div class="p-8 w-full">
      <!-- Show List or Empty State -->
      <template v-if="!showListView && rooms.length === 0">
        <!-- Empty State Page -->
        <div class="flex flex-col items-center justify-center py-32">
          <!-- Icon -->
          <div class="mb-8">
            <svg class="w-24 h-24 text-gray-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M15 10l4.553-2.276A1 1 0 0121 8.618v6.764a1 1 0 01-1.447.894L15 14M5 18h8a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v8a2 2 0 002 2z" />
            </svg>
          </div>

          <!-- Message -->
          <h2 class="text-2xl font-light text-gray-900 mb-6">Waiting for your close up...</h2>
          
          <!-- Description -->
          <p class="text-gray-600 text-center max-w-2xl mb-8">
            SignalWire Video Rooms allow you to take complete control of your video experience providing feature rich building blocks you can use to customize your application.
          </p>

          <p class="text-gray-600 text-center max-w-2xl mb-8">
            They can be used in any website or application and provide low-level control via our REST SDK and RealTime APIs, giving you all the events and control to built anything you can imagine.
          </p>

          <!-- CTA Button -->
          <button
            @click="startCreateRoom"
            class="px-8 py-3 bg-blue-600 text-white font-semibold rounded-full hover:bg-blue-700 transition"
          >
            Create an API Room
          </button>
        </div>
      </template>

      <!-- List View -->
      <template v-else>
        <div class="flex items-center justify-between mb-8">
          <h1 class="text-4xl font-light text-gray-900">Video Conferences</h1>
          <button
            @click="startCreateRoom"
            class="px-6 py-2 bg-blue-600 text-white font-semibold rounded-lg hover:bg-blue-700 transition flex items-center gap-2"
          >
            <span>+</span> New
          </button>
        </div>

        <!-- Rooms Table -->
        <div class="bg-white border border-gray-200 rounded-lg overflow-hidden">
          <table class="w-full">
            <thead class="bg-gray-50 border-b border-gray-200">
              <tr>
                <th class="text-left px-6 py-3 text-sm font-semibold text-gray-900">NAME</th>
                <th class="text-left px-6 py-3 text-sm font-semibold text-gray-900">QUALITY</th>
                <th class="text-left px-6 py-3 text-sm font-semibold text-gray-900">SIZE</th>
                <th class="text-left px-6 py-3 text-sm font-semibold text-gray-900">UI INCLUDED</th>
                <th class="text-right px-6 py-3 text-sm font-semibold text-gray-900"></th>
              </tr>
            </thead>
            <tbody>
              <tr
                v-for="room in rooms"
                :key="room.id"
                class="border-b border-gray-200 hover:bg-gray-50 transition"
              >
                <td class="px-6 py-3">
                  <button
                    @click="editRoom(room)"
                    class="text-gray-900 font-medium hover:text-blue-600"
                  >
                    {{ room.name }}
                  </button>
                </td>
                <td class="px-6 py-3 text-gray-600">{{ room.quality }}</td>
                <td class="px-6 py-3 text-gray-600">{{ room.size }}</td>
                <td class="px-6 py-3 text-gray-600">{{ room.uiIncluded ? 'Yes' : 'No' }}</td>
                <td class="text-right px-6 py-3">
                  <button class="text-gray-400 hover:text-gray-600">
                    <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20">
                      <path d="M10 6a2 2 0 11-4 0 2 2 0 014 0zM10 12a2 2 0 11-4 0 2 2 0 014 0zM10 18a2 2 0 11-4 0 2 2 0 014 0z" />
                    </svg>
                  </button>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </template>

      <!-- Developer Docs Section -->
      <div class="mt-20">
        <div class="flex items-center gap-2 mb-8">
          <h3 class="text-lg font-bold text-gray-900">Developer Docs</h3>
          <button class="text-gray-400 hover:text-gray-600" title="More info">
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd" d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-7-4a1 1 0 11-2 0 1 1 0 012 0zM9 9a1 1 0 000 2v3a1 1 0 001 1h1a1 1 0 100-2v-3a1 1 0 00-1-1H9z" clip-rule="evenodd" />
            </svg>
          </button>
          <a href="#" class="text-blue-600 hover:text-blue-700 font-medium text-sm flex items-center gap-1 ml-auto">
            <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd" d="M18.5 5a1.5 1.5 0 11-3 0 1.5 1.5 0 013 0zm-1.5 3a2.5 2.5 0 11-5 0 2.5 2.5 0 015 0zm-6-1a1.5 1.5 0 11-3 0 1.5 1.5 0 013 0zm-.5 3a2.5 2.5 0 11-5 0 2.5 2.5 0 015 0z" clip-rule="evenodd" />
            </svg>
            Help
          </a>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <!-- Guides Card -->
          <div class="bg-white border border-gray-200 rounded-lg p-6 hover:shadow-lg transition">
            <div class="flex items-start gap-3 mb-4">
              <svg class="w-5 h-5 text-gray-700 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 20 20">
                <path d="M9 4.5a2.5 2.5 0 100 5 2.5 2.5 0 000-5zM5.5 9a4 4 0 118 0 4 4 0 01-8 0z" />
                <path d="M9 15c-3.5 0-6.5 1.5-6.5 3.5S5.5 22 9 22s6.5-1.5 6.5-3.5S12.5 15 9 15z" />
              </svg>
              <h4 class="font-bold text-gray-900">Guides</h4>
            </div>
            <ul class="space-y-2">
              <li>
                <a href="#" class="text-blue-600 hover:text-blue-700 text-sm font-medium">
                  Integrate Video Conferences with any Website
                </a>
              </li>
              <li>
                <a href="#" class="text-blue-600 hover:text-blue-700 text-sm font-medium">
                  First Steps with Video
                </a>
              </li>
            </ul>
          </div>

          <!-- SDK Reference Card -->
          <div class="bg-white border border-gray-200 rounded-lg p-6 hover:shadow-lg transition">
            <div class="flex items-start gap-3 mb-4">
              <svg class="w-5 h-5 text-gray-700 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 20 20">
                <path d="M12.316 3.051a1 1 0 01.633 1.265l-4 12a1 1 0 11-1.898-.633l4-12a1 1 0 011.265-.632zM5.707 6.293a1 1 0 010 1.414L3.414 10l2.293 2.293a1 1 0 11-1.414 1.414l-3-3a1 1 0 010-1.414l3-3a1 1 0 011.414 0zm8.586 0a1 1 0 011.414 0l3 3a1 1 0 010 1.414l-3 3a1 1 0 11-1.414-1.414L16.586 10l-2.293-2.293a1 1 0 010-1.414z" />
              </svg>
              <h4 class="font-bold text-gray-900">SDK Reference</h4>
            </div>
            <ul class="space-y-2">
              <li>
                <a href="#" class="text-blue-600 hover:text-blue-700 text-sm font-medium">
                  RELAY Realtime SDK
                </a>
              </li>
              <li>
                <a href="#" class="text-blue-600 hover:text-blue-700 text-sm font-medium">
                  RELAY Browser SDK
                </a>
              </li>
            </ul>
          </div>

          <!-- REST API Reference Card -->
          <div class="bg-white border border-gray-200 rounded-lg p-6 hover:shadow-lg transition">
            <div class="flex items-start gap-3 mb-4">
              <svg class="w-5 h-5 text-gray-700 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 20 20">
                <path d="M3 4a1 1 0 011-1h12a1 1 0 011 1v2a1 1 0 01-1 1H4a1 1 0 01-1-1V4zM3 10a1 1 0 011-1h12a1 1 0 011 1v6a1 1 0 01-1 1H4a1 1 0 01-1-1v-6z" />
              </svg>
              <h4 class="font-bold text-gray-900">REST API Reference</h4>
            </div>
            <ul class="space-y-2">
              <li>
                <a href="#" class="text-blue-600 hover:text-blue-700 text-sm font-medium">
                  Video Conferences
                </a>
              </li>
              <li>
                <a href="#" class="text-blue-600 hover:text-blue-700 text-sm font-medium">
                  Room Tokens
                </a>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>

    <!-- Step 1: Choose Room Type Modal -->
    <Teleport to="body">
      <transition
        enter-active-class="transition duration-200"
        enter-from-class="opacity-0"
        enter-to-class="opacity-100"
        leave-active-class="transition duration-200"
        leave-from-class="opacity-100"
        leave-to-class="opacity-0"
      >
        <div v-if="showModal && currentStep === 1" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50">
          <transition
            enter-active-class="transition duration-200"
            enter-from-class="opacity-0 scale-95"
            enter-to-class="opacity-100 scale-100"
            leave-active-class="transition duration-200"
            leave-from-class="opacity-100 scale-100"
            leave-to-class="opacity-0 scale-95"
          >
            <div v-if="showModal && currentStep === 1" class="bg-white rounded-lg shadow-xl max-w-2xl w-full mx-4">
              <!-- Modal Header -->
              <div class="border-b border-gray-200 px-8 py-6">
                <h2 class="text-2xl font-bold text-gray-900">New Video Conference Room</h2>
              </div>

              <!-- Modal Body -->
              <div class="p-8">
                <!-- Room Name Input -->
                <div class="mb-8">
                  <label class="block text-sm font-semibold text-gray-900 mb-2">Room Name</label>
                  <input
                    v-model="formData.roomName"
                    type="text"
                    placeholder="Enter room name"
                    class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
                  />
                </div>

                <!-- Room Type Selection -->
                <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-8">
                  <button
                    @click="formData.roomType = 'ui'"
                    :class="[
                      'p-6 rounded-lg border-2 transition text-left',
                      formData.roomType === 'ui'
                        ? 'border-blue-600 bg-blue-50'
                        : 'border-gray-200 hover:border-gray-300'
                    ]"
                  >
                    <div class="flex items-start gap-3">
                      <input
                        type="radio"
                        :checked="formData.roomType === 'ui'"
                        class="mt-1"
                      />
                      <div>
                        <h3 class="font-bold text-gray-900 mb-2">UI Included</h3>
                        <p class="text-sm text-gray-600">
                          No coding required. UI allows you to easily setup and customize video conference rooms and embed them with a single snippet any website or application. They include advanced functionality like device selection, participant lists, room previews, and chat, but also give you access to low level controls, using our real-time SDK and API.
                        </p>
                      </div>
                    </div>
                  </button>

                  <button
                    @click="formData.roomType = 'scratch'"
                    :class="[
                      'p-6 rounded-lg border-2 transition text-left',
                      formData.roomType === 'scratch'
                        ? 'border-blue-600 bg-blue-50'
                        : 'border-gray-200 hover:border-gray-300'
                    ]"
                  >
                    <div class="flex items-start gap-3">
                      <input
                        type="radio"
                        :checked="formData.roomType === 'scratch'"
                        class="mt-1"
                      />
                      <div>
                        <h3 class="font-bold text-gray-900 mb-2">Build From Scratch</h3>
                        <p class="text-sm text-gray-600">
                          Take complete control of your video experience and built a custom implementation using our real-time SDK and API. Receive events and control every aspect of the video conference, no matter what your application.
                        </p>
                        <p class="text-sm text-blue-600 mt-2">
                          See our <a href="#" class="hover:underline">Developer Docs</a> for details.
                        </p>
                      </div>
                    </div>
                  </button>
                </div>

                <!-- Buttons -->
                <div class="flex gap-4 justify-end">
                  <button
                    @click="closeModal"
                    class="px-6 py-2 border border-gray-300 text-gray-900 font-semibold rounded-lg hover:bg-gray-50 transition"
                  >
                    Cancel
                  </button>
                  <button
                    @click="proceedToStep2"
                    class="px-6 py-3 bg-blue-600 text-white font-semibold rounded-lg hover:bg-blue-700 transition"
                  >
                    Next
                  </button>
                </div>
              </div>
            </div>
          </transition>
        </div>
      </transition>
    </Teleport>

    <!-- Step 2: Room Details Modal -->
    <Teleport to="body">
      <transition
        enter-active-class="transition duration-200"
        enter-from-class="opacity-0"
        enter-to-class="opacity-100"
        leave-active-class="transition duration-200"
        leave-from-class="opacity-100"
        leave-to-class="opacity-0"
      >
        <div v-if="showModal && currentStep === 2" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 p-4">
          <transition
            enter-active-class="transition duration-200"
            enter-from-class="opacity-0 scale-95"
            enter-to-class="opacity-100 scale-100"
            leave-active-class="transition duration-200"
            leave-from-class="opacity-100 scale-100"
            leave-to-class="opacity-0 scale-95"
          >
            <div v-if="showModal && currentStep === 2" class="bg-white rounded-lg shadow-xl max-w-3xl w-full max-h-[90vh] overflow-y-auto">
              <!-- Modal Header -->
              <div class="sticky top-0 bg-white border-b border-gray-200 px-8 py-6 flex items-center justify-between">
                <button
                  @click="currentStep = 1"
                  class="text-red-600 hover:text-red-700 font-medium flex items-center gap-1"
                >
                  <span>←</span> Back
                </button>
              </div>

              <!-- Modal Body -->
              <div class="p-8">
                <!-- Room Preview -->
                <div class="mb-8">
                  <div class="bg-black rounded-lg h-64 flex items-center justify-center mb-4 relative">
                    <div class="text-gray-400 text-center">
                      <div class="mb-2">📹</div>
                      <p>Room preview area</p>
                    </div>
                  </div>
                  <p class="text-sm text-gray-600">Turn on Room Previews to see snapshots of in-progress rooms here.</p>
                </div>

                <!-- Control Buttons -->
                <div class="space-y-3 mb-8">
                  <button class="w-full px-4 py-3 bg-blue-600 text-white font-semibold rounded-full hover:bg-blue-700 transition">
                    Join Room as Moderator
                  </button>
                  <button class="w-full px-4 py-2 border-2 border-blue-600 text-blue-600 font-semibold rounded-full hover:bg-blue-50 transition">
                    Copy Moderator Link
                  </button>
                  <button class="w-full px-4 py-2 border-2 border-blue-600 text-blue-600 font-semibold rounded-full hover:bg-blue-50 transition">
                    Moderator Embed Code
                  </button>
                  <button class="w-full px-4 py-2 border-2 border-blue-600 text-blue-600 font-semibold rounded-full hover:bg-blue-50 transition">
                    Copy Moderator Token
                  </button>
                  <button class="w-full px-4 py-2 border-2 border-blue-600 text-blue-600 font-semibold rounded-full hover:bg-blue-50 transition">
                    Reset Tokens
                  </button>
                </div>

                <!-- Tabs -->
                <div class="border-b border-gray-200 mb-6">
                  <div class="flex gap-8">
                    <button
                      @click="activeTab = 'settings'"
                      :class="[
                        'py-3 font-medium transition-colors',
                        activeTab === 'settings'
                          ? 'text-gray-900 border-b-2 border-gray-900'
                          : 'text-gray-600 hover:text-gray-900'
                      ]"
                    >
                      Settings
                    </button>
                    <button
                      @click="activeTab = 'appearance'"
                      :class="[
                        'py-3 font-medium transition-colors',
                        activeTab === 'appearance'
                          ? 'text-gray-900 border-b-2 border-gray-900'
                          : 'text-gray-600 hover:text-gray-900'
                      ]"
                    >
                      Appearance
                    </button>
                    <button
                      @click="activeTab = 'streaming'"
                      :class="[
                        'py-3 font-medium transition-colors',
                        activeTab === 'streaming'
                          ? 'text-gray-900 border-b-2 border-gray-900'
                          : 'text-gray-600 hover:text-gray-900'
                      ]"
                    >
                      Streaming
                    </button>
                  </div>
                </div>

                <!-- Settings Tab -->
                <div v-show="activeTab === 'settings'" class="space-y-6 mb-8">
                  <!-- Availability -->
                  <div>
                    <h3 class="font-bold text-gray-900 mb-2">Availability</h3>
                    <p class="text-sm text-gray-600 mb-4">Members can enter the room only between these times</p>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                      <div>
                        <label class="block text-sm font-medium text-gray-700 mb-1">From - Optional</label>
                        <input
                          type="text"
                          placeholder="mm/dd/yyyy, --:--"
                          class="w-full px-3 py-2 border border-gray-300 rounded-lg focus:outline-none"
                        />
                      </div>
                      <div>
                        <label class="block text-sm font-medium text-gray-700 mb-1">Until - Optional</label>
                        <input
                          type="text"
                          placeholder="mm/dd/yyyy, --:--"
                          class="w-full px-3 py-2 border border-gray-300 rounded-lg focus:outline-none"
                        />
                      </div>
                    </div>
                  </div>

                  <!-- Quality -->
                  <div class="border-t border-gray-200 pt-6">
                    <h3 class="font-bold text-gray-900 mb-4">Quality</h3>
                    <p class="text-sm text-gray-600 mb-4">Quality of the room's video feed.</p>
                    <div class="space-y-2">
                      <label class="flex items-center gap-3">
                        <input type="radio" v-model="formData.quality" value="720p" />
                        <span class="text-gray-900">720p</span>
                      </label>
                      <label class="flex items-center gap-3">
                        <input type="radio" v-model="formData.quality" value="1080p" />
                        <span class="text-gray-900">1080p</span>
                      </label>
                    </div>
                  </div>

                  <!-- Layout -->
                  <div class="border-t border-gray-200 pt-6">
                    <h3 class="font-bold text-gray-900 mb-2">Layout</h3>
                    <p class="text-sm text-gray-600 mb-4">Layout controls how participants are arranged on screen.</p>
                    <select class="w-full px-3 py-2 border border-gray-300 rounded-lg bg-white focus:outline-none">
                      <option>grid-responsive</option>
                      <option>speaker</option>
                      <option>picture-in-picture</option>
                    </select>
                  </div>

                  <!-- Size -->
                  <div class="border-t border-gray-200 pt-6">
                    <h3 class="font-bold text-gray-900 mb-4">Size</h3>
                    <p class="text-sm text-gray-600 mb-4">Maximum number of members allowed in the room at a time.</p>
                    <div class="grid grid-cols-3 gap-4">
                      <label class="flex items-center gap-2">
                        <input type="radio" v-model="formData.size" value="small" />
                        <div>
                          <p class="font-medium text-gray-900">Small</p>
                          <p class="text-xs text-gray-600">Max 10</p>
                        </div>
                      </label>
                      <label class="flex items-center gap-2">
                        <input type="radio" v-model="formData.size" value="medium" />
                        <div>
                          <p class="font-medium text-gray-900">Medium</p>
                          <p class="text-xs text-gray-600">Max 50</p>
                        </div>
                      </label>
                      <label class="flex items-center gap-2">
                        <input type="radio" v-model="formData.size" value="large" />
                        <div>
                          <p class="font-medium text-gray-900">Large</p>
                          <p class="text-xs text-gray-600">Max 300</p>
                        </div>
                      </label>
                    </div>
                  </div>

                  <!-- Toggles -->
                  <div class="border-t border-gray-200 pt-6 space-y-4">
                    <div class="flex items-center justify-between">
                      <div>
                        <h3 class="font-bold text-gray-900">Record on Start</h3>
                        <p class="text-sm text-gray-600">Automatically start recording the room as soon as it starts.</p>
                      </div>
                      <label class="flex items-center cursor-pointer">
                        <input type="checkbox" v-model="formData.recordOnStart" />
                        <span class="ml-2 text-sm">{{ formData.recordOnStart ? 'Yes' : 'No' }}</span>
                      </label>
                    </div>

                    <div class="flex items-center justify-between">
                      <div>
                        <h3 class="font-bold text-gray-900">Enable Room Previews</h3>
                        <p class="text-sm text-gray-600">People will be able to see inside the room without joining.</p>
                      </div>
                      <label class="flex items-center cursor-pointer">
                        <input type="checkbox" v-model="formData.enablePreviews" />
                        <span class="ml-2 text-sm">{{ formData.enablePreviews ? 'Yes' : 'No' }}</span>
                      </label>
                    </div>

                    <div class="flex items-center justify-between">
                      <div>
                        <h3 class="font-bold text-gray-900">Enable Chat</h3>
                        <p class="text-sm text-gray-600">Group chat will be available to all participants in the room.</p>
                      </div>
                      <label class="flex items-center cursor-pointer">
                        <input type="checkbox" v-model="formData.enableChat" />
                        <span class="ml-2 text-sm">{{ formData.enableChat ? 'Yes' : 'No' }}</span>
                      </label>
                    </div>

                    <div class="flex items-center justify-between">
                      <div>
                        <h3 class="font-bold text-gray-900">Play Sound on Entry and Exit</h3>
                        <p class="text-sm text-gray-600">Play a notification sound when participants join or leave the room.</p>
                      </div>
                      <label class="flex items-center cursor-pointer">
                        <input type="checkbox" v-model="formData.playSoundOnEntry" />
                        <span class="ml-2 text-sm">{{ formData.playSoundOnEntry ? 'Yes' : 'No' }}</span>
                      </label>
                    </div>

                    <div class="flex items-center justify-between">
                      <div>
                        <h3 class="font-bold text-gray-900">Room Join Video Off</h3>
                        <p class="text-sm text-gray-600">Automatically turn off video for all participants when they join the room.</p>
                      </div>
                      <label class="flex items-center cursor-pointer">
                        <input type="checkbox" v-model="formData.joinVideoOff" />
                        <span class="ml-2 text-sm">{{ formData.joinVideoOff ? 'Yes' : 'No' }}</span>
                      </label>
                    </div>
                  </div>

                  <!-- Room Description -->
                  <div class="border-t border-gray-200 pt-6">
                    <h3 class="font-bold text-gray-900 mb-2">Room Description</h3>
                    <p class="text-sm text-gray-600 mb-2">Add a description to your room. Must be under 3000 characters.</p>
                    <textarea
                      v-model="formData.description"
                      class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
                      rows="4"
                    ></textarea>
                  </div>

                  <!-- Save Button -->
                  <div class="border-t border-gray-200 pt-6">
                    <button class="w-full px-6 py-3 bg-blue-600 text-white font-semibold rounded-lg hover:bg-blue-700 transition">
                      Save
                    </button>
                  </div>

                  <!-- Delete Room -->
                  <div class="border-t border-gray-200 pt-6">
                    <h3 class="font-bold text-gray-900 mb-2">Delete Room</h3>
                    <p class="text-sm text-gray-600 mb-4">Deleting this room won't effect any in-progress sessions, but new sessions will not be started and all tokens will be invalidated. This cannot be undone.</p>
                    <button class="px-6 py-2 border-2 border-red-600 text-red-600 font-semibold rounded-full hover:bg-red-50 transition">
                      Delete Room
                    </button>
                  </div>
                </div>

                <!-- Appearance Tab -->
                <div v-show="activeTab === 'appearance'" class="space-y-6 mb-8">
                  <div>
                    <h3 class="font-bold text-gray-900 mb-4">Colors</h3>
                    <div class="grid grid-cols-2 gap-8">
                      <div>
                        <h4 class="font-medium text-gray-900 mb-3">Background</h4>
                        <div class="flex gap-4">
                          <div class="w-8 h-8 bg-white border border-gray-300 rounded"></div>
                          <div class="w-8 h-8 bg-black rounded"></div>
                        </div>
                      </div>
                      <div>
                        <h4 class="font-medium text-gray-900 mb-3">Preview</h4>
                        <div class="w-32 h-32 bg-black rounded"></div>
                      </div>
                    </div>
                  </div>
                  <button class="w-full px-6 py-3 bg-blue-600 text-white font-semibold rounded-lg hover:bg-blue-700 transition">
                    Save
                  </button>
                </div>

                <!-- Streaming Tab -->
                <div v-show="activeTab === 'streaming'" class="space-y-6 mb-8">
                  <div class="text-center py-12">
                    <div class="text-4xl mb-4">🎙️</div>
                    <h3 class="font-bold text-gray-900 mb-2">Stream Your Room</h3>
                    <p class="text-gray-600 mb-6">
                      Streams will start publishing a video feed of your room once it starts, allowing you to share what happens in your rooms across social platforms your or own private streaming server.
                    </p>
                    <button class="px-6 py-3 bg-blue-600 text-white font-semibold rounded-full hover:bg-blue-700 transition">
                      Setup a Stream
                    </button>
                  </div>

                  <!-- New Stream Section -->
                  <div class="border-t border-gray-200 pt-6">
                    <h3 class="font-bold text-gray-900 mb-2">New Video Stream</h3>
                    <p class="text-sm text-gray-600 mb-4">
                      Enter the URL where the room's video stream will be sent. This can be any RTMP/RTMPS location. Most streaming platforms will provide an RTMP stream URL, enter that value below to automatically initiate a stream everytime a room starts.
                    </p>
                    <div class="mb-4">
                      <label class="block text-sm font-semibold text-gray-900 mb-2">Stream URL</label>
                      <input
                        type="text"
                        placeholder="rtmps://my-server.com"
                        class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:outline-none"
                      />
                      <p class="text-xs text-gray-600 mt-2">Enter the URL of where the video stream should be sent. Only RTMP and RTMPS are supported.</p>
                    </div>
                    <button class="px-6 py-2 bg-blue-600 text-white font-semibold rounded-lg hover:bg-blue-700 transition">
                      Save
                    </button>
                  </div>

                  <!-- Delete Room -->
                  <div class="border-t border-gray-200 pt-6">
                    <h3 class="font-bold text-gray-900 mb-2">Delete Room</h3>
                    <p class="text-sm text-gray-600 mb-4">Deleting this room won't effect any in-progress sessions, but new sessions will not be started and all tokens will be invalidated. This cannot be undone.</p>
                    <button class="px-6 py-2 border-2 border-red-600 text-red-600 font-semibold rounded-full hover:bg-red-50 transition">
                      Delete Room
                    </button>
                  </div>
                </div>
              </div>
            </div>
          </transition>
        </div>
      </transition>
    </Teleport>

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
import DashboardLayout from '@/components/dashboard/DashboardLayout.vue'

const showModal = ref(false)
const showListView = ref(false)
const currentStep = ref(1)
const activeTab = ref('settings')

const formData = ref({
  roomName: '',
  roomType: 'ui',
  quality: '720p',
  size: 'medium',
  recordOnStart: false,
  enablePreviews: false,
  enableChat: true,
  playSoundOnEntry: true,
  joinVideoOff: false,
  description: ''
})

const rooms = ref([
  {
    id: 1,
    name: 'testing',
    quality: '720p',
    size: 'Medium',
    uiIncluded: true
  }
])

const startCreateRoom = () => {
  showModal.value = true
  currentStep.value = 1
  formData.value = {
    roomName: '',
    roomType: 'ui',
    quality: '720p',
    size: 'medium',
    recordOnStart: false,
    enablePreviews: false,
    enableChat: true,
    playSoundOnEntry: true,
    joinVideoOff: false,
    description: ''
  }
}

const proceedToStep2 = () => {
  if (formData.value.roomName.trim()) {
    currentStep.value = 2
    showListView.value = true
  }
}

const editRoom = (room) => {
  startCreateRoom()
  formData.value.roomName = room.name
  currentStep.value = 2
}

const closeModal = () => {
  showModal.value = false
  currentStep.value = 1
}
</script>

<style scoped>
.transition {
  transition-duration: 200ms;
}
</style>