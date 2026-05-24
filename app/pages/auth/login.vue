<template>
  <Layout>
    <div class="min-h-screen bg-gradient-to-br from-blue-50 to-blue-100 pt-20">
      <!-- Main Content -->
      <div class="flex items-center justify-center px-4 py-12">
        <div class="w-full max-w-7xl grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
          <!-- Left: Login Form -->
          <div class="bg-white rounded-lg shadow-lg p-8 h-fit">
            <h1 class="text-3xl font-bold text-gray-900 mb-8">Log in to your Flowdacity account</h1>

            <form @submit.prevent="handleLogin" class="space-y-6">
              <!-- Work Email -->
              <div>
                <input v-model="formData.email" type="email" placeholder="Work Email" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500" required />
              </div>

              <!-- Password -->
              <div>
                <input v-model="formData.password" type="password" placeholder="Password" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500" required />
              </div>

              <!-- Forgot Password -->
              <div class="text-right">
                <a href="#" class="text-green-600 hover:text-green-700 font-medium text-sm">Forgot Password?</a>
              </div>

              <!-- Submit Button -->
              <button type="submit" class="w-full bg-green-600 text-white font-bold py-3 rounded-lg uppercase text-sm">Log in</button>
            </form>

            <div class="mt-6 text-center text-sm text-gray-600 space-y-2">
              <p>
                Don't have an account?
                <NuxtLink to="/auth/signup" class="text-green-600 hover:text-green-700 font-semibold">Sign Up</NuxtLink>
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
              <div class="bg-white rounded-lg shadow-lg p-8 relative overflow-hidden">
                <div class="absolute top-4 right-4 w-32 h-32 opacity-10"></div>
                <div class="absolute top-8 right-8 text-6xl opacity-20">🌍</div>
                <div class="relative z-10">
                  <div class="inline-block bg-green-100 text-green-700 px-3 py-1 rounded-full text-xs font-semibold mb-4 uppercase">NEW</div>
                  <div class="grid grid-cols-3 gap-3 mb-6">
                    <div class="flex items-center justify-center w-10 h-10 bg-green-100 rounded text-xl">📞</div>
                    <div class="flex items-center justify-center w-10 h-10 bg-green-100 rounded text-xl">👥</div>
                    <div class="flex items-center justify-center w-10 h-10 bg-green-100 rounded text-xl">📱</div>
                  </div>
                  <h3 class="text-2xl font-bold text-gray-900 mb-3">Zentrunk - Cloud based SIP trunking</h3>
                  <p class="text-gray-600 mb-6 leading-relaxed">Global Connectivity, Unlimited Concurrent Calls with Flexible Pay-as-you-go Pricing. Connect your VoIP infrastructure in minutes.</p>

                  <a href="#" class="text-green-600 hover:text-green-700 font-semibold">Learn more →</a>
                </div>
              </div>
              <div class="text-sm text-gray-600 px-4">Access all Flowdacity products with a single login</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </Layout>
</template>

<script setup>
import Layout from '../../components/Layout.vue'
import { ref } from 'vue'

const formData = ref({ email: '', password: '' })
function handleLogin() {
  // placeholder for actual login logic
}
</script>

<style scoped>
</style>
