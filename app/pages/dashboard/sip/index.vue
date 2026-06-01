<template>
  <DashboardLayout>
    <div class="p-8 w-full max-w-4xl">
      <!-- Page Title -->
      <h1 class="text-4xl font-light text-gray-900 mb-12">New Domain App</h1>

      <!-- Form Container -->
      <form @submit.prevent="saveDomainApp" class="space-y-12">
        <!-- Name Section -->
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
          <div>
            <p class="text-gray-600">Give this domain app a friendly name to more easily find and search for it later.</p>
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-2">Name</label>
            <input
              v-model="formData.name"
              type="text"
              placeholder="My Domain App"
              class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
            />
          </div>
        </div>

        <hr class="border-gray-200" />

        <!-- SIP Host URL Section -->
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
          <div>
            <h2 class="text-lg font-bold text-gray-900 mb-2">SIP Host URL</h2>
            <p class="text-gray-600 text-sm">Customize the host portion of the SIP URI for this domain app. Each Domain App has a unique SIP Host, allowing you to easily direct traffic to this application.</p>
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-2">App URL</label>
            <div class="flex items-center gap-2">
              <span class="text-gray-600">pecwill-</span>
              <input
                v-model="formData.appUrl"
                type="text"
                placeholder="myapp"
                maxlength="50"
                class="flex-1 px-3 py-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
              />
              <span class="text-gray-600">.dapp.signalwire.com</span>
            </div>
            <p class="text-xs text-gray-600 mt-2">Must be letters, numbers, and dash only. Maximum 50 characters.</p>
          </div>
        </div>

        <hr class="border-gray-200" />

        <!-- Password Section -->
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
          <div>
            <h2 class="text-lg font-bold text-gray-900 mb-2">Password</h2>
            <p class="text-gray-600 text-sm">An optional password to allow calls to be routed to this domain application.</p>
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-2">Password</label>
            <button
              type="button"
              @click="showPasswordModal = true"
              class="px-6 py-2 bg-blue-600 text-white font-semibold rounded-full hover:bg-blue-700 transition"
            >
              New Password
            </button>
          </div>
        </div>

        <hr class="border-gray-200" />

        <!-- IP Whitelisting Section -->
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
          <div>
            <h2 class="text-lg font-bold text-gray-900 mb-2">IP Whitelisting</h2>
            <p class="text-gray-600 text-sm">Authorize specific IPs to send requests to this domain. You can choose individual IPs or use CIDR notation to authorize a range of IPs.</p>
          </div>
          <div>
            <div class="flex items-center gap-4">
              <label class="flex items-center gap-2">
                <input type="radio" v-model="formData.ipWhitelisting" :value="false" />
                <span class="text-gray-900">Off</span>
              </label>
              <label class="flex items-center gap-2">
                <input type="radio" v-model="formData.ipWhitelisting" :value="true" />
                <span class="text-gray-900">On</span>
              </label>
            </div>
          </div>
        </div>

        <hr class="border-gray-200" />

        <!-- Inbound Call Settings Section -->
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
          <div>
            <h2 class="text-lg font-bold text-gray-900 mb-2">Inbound Call Settings</h2>
            <p class="text-gray-600 text-sm">Determine what happens when an inbound call is received.</p>
            <p class="text-gray-600 text-sm mt-3">When an inbound call is received, designate a resource to handle the logic of what to do when the call is received and how to notify you and your application.</p>
          </div>
          <div class="space-y-4">
            <div>
              <label class="block text-sm font-medium text-gray-700 mb-2">Handle Using</label>
              <select v-model="formData.handleUsing" class="w-full px-4 py-2 border border-gray-300 rounded-lg bg-white focus:outline-none focus:ring-2 focus:ring-blue-500">
                <option>Relay Application</option>
                <option>LaML Application</option>
              </select>
            </div>

            <div>
              <label class="block text-sm font-medium text-gray-700 mb-2">When A Call Comes In, Forward Call To This Relay Topic:</label>
              <input
                v-model="formData.relayTopic"
                type="text"
                placeholder="topic-name"
                class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
              />
              <p class="text-xs text-gray-600 mt-1">When setting up a Relay client to receive calls, you specify a topic to determine which calls to receive.</p>
            </div>

            <div>
              <label class="block text-sm font-medium text-gray-700 mb-2">Status Change Webhook: - Optional</label>
              <input
                v-model="formData.webhook"
                type="text"
                placeholder="https://path.to/your/webhook"
                class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
              />
            </div>
          </div>
        </div>

        <hr class="border-gray-200" />

        <!-- Advanced Section -->
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
          <div>
            <h2 class="text-lg font-bold text-gray-900 mb-2">Advanced</h2>
            <p class="text-gray-600 text-sm">Set advanced SIP settings for this endpoint like supported encryption and codes.</p>
          </div>
          <div class="space-y-6">
            <!-- Encryption -->
            <div>
              <label class="block text-sm font-medium text-gray-700 mb-2">Encryption</label>
              <select v-model="formData.encryption" class="w-full px-4 py-2 border border-gray-300 rounded-lg bg-white focus:outline-none focus:ring-2 focus:ring-blue-500">
                <option>Optional</option>
                <option>Required</option>
                <option>Disabled</option>
              </select>
              <p class="text-xs text-gray-600 mt-1">Require encryption, optionally use it if it's available, or disable it entirely.</p>
            </div>

            <!-- Supported Codecs -->
            <div>
              <h3 class="font-semibold text-gray-900 mb-3">Supported Codecs</h3>
              <div class="space-y-2">
                <label class="flex items-center gap-2">
                  <input type="checkbox" v-model="formData.codecs" value="OPUS" />
                  <span class="text-gray-900">OPUS</span>
                </label>
                <label class="flex items-center gap-2">
                  <input type="checkbox" v-model="formData.codecs" value="G722" />
                  <span class="text-gray-900">G722</span>
                </label>
                <label class="flex items-center gap-2">
                  <input type="checkbox" v-model="formData.codecs" value="PCMU" />
                  <span class="text-gray-900">PCMU</span>
                </label>
                <label class="flex items-center gap-2">
                  <input type="checkbox" v-model="formData.codecs" value="PCMA" />
                  <span class="text-gray-900">PCMA</span>
                </label>
                <label class="flex items-center gap-2">
                  <input type="checkbox" v-model="formData.codecs" value="G729" />
                  <span class="text-gray-900">G729</span>
                </label>
                <label class="flex items-center gap-2">
                  <input type="checkbox" v-model="formData.codecs" value="VP8" />
                  <span class="text-gray-900">VP8</span>
                </label>
                <label class="flex items-center gap-2">
                  <input type="checkbox" v-model="formData.codecs" value="H264" />
                  <span class="text-gray-900">H2665</span>
                </label>
              </div>
              <p class="text-xs text-gray-600 mt-2">Which codecs do you want to support. You must choose at least one.</p>
            </div>

            <!-- Supported Ciphers -->
            <div>
              <h3 class="font-semibold text-gray-900 mb-3">Supported Ciphers</h3>
              <div class="space-y-2">
                <label class="flex items-center gap-2">
                  <input type="checkbox" v-model="formData.ciphers" value="AEAD_AES_256_GCM_8" />
                  <span class="text-gray-900 text-sm">AEAD_AES_256_GCM_8</span>
                </label>
                <label class="flex items-center gap-2">
                  <input type="checkbox" v-model="formData.ciphers" value="AES_256_CM_HMAC_SHA1_80" />
                  <span class="text-gray-900 text-sm">AES_256_CM_HMAC_SHA1_80</span>
                </label>
                <label class="flex items-center gap-2">
                  <input type="checkbox" v-model="formData.ciphers" value="AES_CM_128_HMAC_SHA1_80" />
                  <span class="text-gray-900 text-sm">AES_CM_128_HMAC_SHA1_80</span>
                </label>
                <label class="flex items-center gap-2">
                  <input type="checkbox" v-model="formData.ciphers" value="AES_256_CM_HMAC_SHA1_32" />
                  <span class="text-gray-900 text-sm">AES_256_CM_HMAC_SHA1_32</span>
                </label>
                <label class="flex items-center gap-2">
                  <input type="checkbox" v-model="formData.ciphers" value="AES_CM_128_HMAC_SHA1_32" />
                  <span class="text-gray-900 text-sm">AES_CM_128_HMAC_SHA1_32</span>
                </label>
              </div>
              <p class="text-xs text-gray-600 mt-2">Which ciphers do you want to support. You must choose at least one.</p>
            </div>
          </div>
        </div>

        <hr class="border-gray-200" />

        <!-- Save Button -->
        <div class="flex justify-start">
          <button
            type="submit"
            class="px-12 py-3 bg-blue-600 text-white font-semibold rounded-full hover:bg-blue-700 transition"
          >
            Save
          </button>
        </div>
      </form>
    </div>

  
  </DashboardLayout>
</template>

<script setup>
import { ref } from 'vue'
import DashboardLayout from '@/components/dashboard/DashboardLayout.vue'

const showPasswordModal = ref(false)

const formData = ref({
  name: '',
  appUrl: '',
  ipWhitelisting: false,
  handleUsing: 'Relay Application',
  relayTopic: '',
  webhook: '',
  encryption: 'Optional',
  codecs: [],
  ciphers: []
})

const saveDomainApp = () => {
  // Validate form
  if (!formData.value.name) {
    alert('Please enter a name')
    return
  }
  if (!formData.value.appUrl) {
    alert('Please enter an app URL')
    return
  }
  if (formData.value.codecs.length === 0) {
    alert('Please select at least one codec')
    return
  }
  if (formData.value.ciphers.length === 0) {
    alert('Please select at least one cipher')
    return
  }

  // Submit form
  console.log('Saving Domain App:', formData.value)
  // Send to API
}
</script>

<style scoped>
.transition {
  transition-duration: 200ms;
}
</style>