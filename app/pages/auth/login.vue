<template>
  <div class="min-h-screen bg-gradient-to-br from-blue-50 to-blue-100">
    <!-- Header with Logo and Links -->
    <nav class="flex items-center justify-between px-8 py-6">
      <div class="flex items-center gap-2">
        <div class="w-8 h-8 bg-green-500 rounded-full flex items-center justify-center">
          <span class="text-white font-bold text-lg">P</span>
        </div>
        <span class="text-xl font-bold text-gray-900">plivo</span>
      </div>

      <div class="flex items-center gap-6">
        <a href="#" class="text-gray-700 hover:text-gray-900 font-medium">Docs</a>
        <a href="#" class="text-gray-700 hover:text-gray-900 font-medium">Support</a>
      </div>
    </nav>

    <!-- Main Content -->
    <div class="flex items-center justify-center px-4 py-12">
      <div class="w-full max-w-7xl grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
        <!-- Left: Login Form -->
        <div class="bg-white rounded-lg shadow-lg p-8 h-fit">
          <h1 class="text-3xl font-bold text-gray-900 mb-8">Log in to your Plivo account</h1>

          <!-- Form -->
          <form @submit.prevent="handleLogin" class="space-y-6">
            <!-- Work Email -->
            <div>
              <input
                v-model="formData.email"
                type="email"
                placeholder="Work Email"
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500 focus:border-transparent"
                required
              />
            </div>

            <!-- Password -->
            <div>
              <input
                v-model="formData.password"
                type="password"
                placeholder="Password"
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500 focus:border-transparent"
                required
              />
            </div>

            <!-- Forgot Password -->
            <div class="text-right">
              <a href="#" class="text-green-600 hover:text-green-700 font-medium text-sm">Forgot Password?</a>
            </div>

            <!-- Submit Button -->
            <button
              type="submit"
              class="w-full bg-green-600 text-white font-bold py-3 rounded-lg hover:bg-green-700 transition duration-200 uppercase text-sm"
            >
              Log in
            </button>
          </form>

          <!-- Sign Up Links -->
          <div class="mt-6 text-center text-sm text-gray-600 space-y-2">
            <p>
              Don't have an account?
              <NuxtLink to="/signup" class="text-green-600 hover:text-green-700 font-semibold">Sign Up</NuxtLink>
            </p>
            <p>
              Did not receive an activation mail?
              <a href="#" class="text-green-600 hover:text-green-700 font-semibold">Resend Activation E-mail</a>
            </p>
          </div>
        </div>

        <!-- Right: Feature Showcase -->
        <div class="hidden lg:block">
          <div class="space-y-8">
            <!-- Feature Card -->
            <div class="bg-white rounded-lg shadow-lg p-8 relative overflow-hidden">
              <!-- Illustration Grid -->
              <div class="absolute top-4 right-4 w-32 h-32 opacity-10">
                <div class="grid grid-cols-2 gap-2 h-full">
                  <div class="bg-green-300 rounded"></div>
                  <div class="bg-green-400 rounded"></div>
                  <div class="bg-green-500 rounded"></div>
                  <div class="bg-green-600 rounded"></div>
                </div>
              </div>

              <!-- Globe Icon -->
              <div class="absolute top-8 right-8 text-6xl opacity-20">
                🌍
              </div>

              <!-- Content -->
              <div class="relative z-10">
                <!-- Badge -->
                <div class="inline-block bg-green-100 text-green-700 px-3 py-1 rounded-full text-xs font-semibold mb-4 uppercase">
                  NEW
                </div>

                <!-- Icons Grid -->
                <div class="grid grid-cols-3 gap-3 mb-6">
                  <div class="flex items-center justify-center w-10 h-10 bg-green-100 rounded text-xl">📞</div>
                  <div class="flex items-center justify-center w-10 h-10 bg-green-100 rounded text-xl">👥</div>
                  <div class="flex items-center justify-center w-10 h-10 bg-green-100 rounded text-xl">📱</div>
                  <div class="flex items-center justify-center w-10 h-10 bg-green-100 rounded text-xl">💬</div>
                  <div class="flex items-center justify-center w-10 h-10 bg-green-100 rounded text-xl">🌐</div>
                  <div class="flex items-center justify-center w-10 h-10 bg-green-100 rounded text-xl">📊</div>
                </div>

                <!-- Title and Description -->
                <h3 class="text-2xl font-bold text-gray-900 mb-3">Zentrunk - Cloud based SIP trunking</h3>
                <p class="text-gray-600 mb-6 leading-relaxed">
                  Global Connectivity, Unlimited Concurrent Calls with Flexible Pay-as-you-go Pricing. Connect your VoIP infrastructure in minutes.
                </p>

                <!-- Learn More Link -->
                <a href="#" class="text-green-600 hover:text-green-700 font-semibold">Learn more →</a>
              </div>
            </div>

            <!-- Additional Info -->
            <div class="text-sm text-gray-600 px-4">
              <p>Access all Plivo products with a single login</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const formData = ref({
  email: '',
  password: ''
})

const handleLogin = () => {
  console.log('Login data:', formData.value)
  // Add your login logic here
  alert('Login successful! (This is a demo)')
}
</script>

<style scoped>
/* Add any additional styles here */
</style>