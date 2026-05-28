<template>
  <DashboardLayout>
    <div class="p-8 w-full">
      <!-- Page Title -->
      <h1 class="text-4xl font-light text-gray-900 mb-16">Dialogflow Agents</h1>

      <!-- Empty State -->
      <div class="flex flex-col items-center justify-center py-24">
        <!-- Icon -->
        <div class="mb-8">
          <div class="w-24 h-24 bg-blue-600 rounded-full flex items-center justify-center shadow-lg">
            <svg class="w-12 h-12 text-white" fill="currentColor" viewBox="0 0 24 24">
              <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8zm3.5-9c.83 0 1.5-.67 1.5-1.5S16.33 8 15.5 8 14 8.67 14 9.5s.67 1.5 1.5 1.5zm-7 0c.83 0 1.5-.67 1.5-1.5S9.33 8 8.5 8 7 8.67 7 9.5 7.67 11 8.5 11zm3.5 6.5c2.33 0 4.31-1.46 5.11-3.5H6.89c.8 2.04 2.78 3.5 5.11 3.5z" />
            </svg>
          </div>
        </div>

        <!-- Message -->
        <h2 class="text-3xl font-light text-gray-900 mb-6">No Dialogflow Agents yet...</h2>

        <!-- Description -->
        <p class="text-gray-600 text-center max-w-2xl mb-4">
          Dialogflow is a service for building conversational interfaces for websites, mobile applications, and IoT devices. You can use it to build interfaces that are capable of natural and rich interactions between your users and your business. It is powered by machine learning to recognize the intent and context of what a user says, allowing your conversational interface to provide highly efficient and accurate responses.
        </p>

        <p class="text-gray-600 text-center max-w-2xl mb-8">
          With SignalWire, you can link your Dialogflow agents to your SignalWire phone numbers to build powerful and intelligent applications and interactions.
        </p>

        <!-- CTA Button -->
        <button
          @click="showImportModal = true"
          class="px-8 py-3 bg-blue-600 text-white font-semibold rounded-full hover:bg-blue-700 transition"
        >
          Import a Dialogflow Agent
        </button>
      </div>

      <!-- Developer Docs Section -->
      <div class="mt-24">
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
                  Integrating Dialogflow
                </a>
              </li>
              <li>
                <a href="#" class="text-blue-600 hover:text-blue-700 text-sm font-medium">
                  Sending SMS via Dialogflow
                </a>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>

    <!-- Import Dialogflow Agent Modal -->
    <Teleport to="body">
      <transition
        enter-active-class="transition duration-200"
        enter-from-class="opacity-0"
        enter-to-class="opacity-100"
        leave-active-class="transition duration-200"
        leave-from-class="opacity-100"
        leave-to-class="opacity-0"
      >
        <div v-if="showImportModal" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 p-4">
          <transition
            enter-active-class="transition duration-200"
            enter-from-class="opacity-0 scale-95"
            enter-to-class="opacity-100 scale-100"
            leave-active-class="transition duration-200"
            leave-from-class="opacity-100 scale-100"
            leave-to-class="opacity-0 scale-95"
          >
            <div v-if="showImportModal" class="bg-white rounded-lg shadow-xl w-full max-w-md">
              <!-- Modal Header -->
              <div class="border-b border-gray-200 px-6 py-6">
                <h2 class="text-2xl font-bold text-gray-900">Import a Dialogflow Agent</h2>
              </div>

              <!-- Modal Body -->
              <div class="p-6">
                <!-- Instructions -->
                <div class="space-y-4 mb-6">
                  <p class="text-gray-900">
                    To add a Dialogflow Agent to your SignalWire project, start by enabling the
                    <span class="font-semibold">SignalWire Telephony Integration</span>
                    from the Dialogflow Console.
                  </p>

                  <p class="text-gray-600">
                    This will import your agent into your SignalWire project and allow you to integrate your Agent with SignalWire phone numbers, applications, and more.
                  </p>
                </div>

                <!-- CTA Button -->
                <button
                  @click="openDialogflowConsole"
                  class="w-full px-6 py-3 bg-blue-600 text-white font-semibold rounded-full hover:bg-blue-700 transition flex items-center justify-center gap-2 mb-6"
                >
                  Go to Dialogflow Console
                  <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14" />
                  </svg>
                </button>

                <!-- Tutorial Link -->
                <div class="border-t border-gray-200 pt-6 text-center">
                  <p class="text-sm text-gray-600 mb-2">For more help, see our tutorial:</p>
                  <a href="#" class="text-blue-600 hover:text-blue-700 font-medium text-sm">
                    Importing your Dialogflow Agent to SignalWire
                  </a>
                </div>

                <!-- Close Button -->
                <button
                  @click="closeImportModal"
                  class="w-full mt-6 px-6 py-2 text-gray-600 font-semibold hover:text-gray-900 transition"
                >
                  Close
                </button>
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
import DashboardLayout from '../../../components/DashboardLayout.vue'

const showImportModal = ref(false)

const openDialogflowConsole = () => {
  // Open Dialogflow console in a new tab
  window.open('https://dialogflow.cloud.google.com/', '_blank')
}

const closeImportModal = () => {
  showImportModal.value = false
}
</script>

<style scoped>
.transition {
  transition-duration: 200ms;
}
</style>