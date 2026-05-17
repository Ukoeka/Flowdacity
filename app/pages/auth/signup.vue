<template>
  <Layout>
    <div class="min-h-screen bg-gradient-to-br from-blue-50 to-blue-100 flex items-center justify-center px-4 py-8">
      <div class="w-full max-w-md">
        <div class="bg-white rounded-lg shadow-lg p-8">
          <h1 class="text-3xl font-bold text-gray-900 mb-8 text-center">Create your Plivo Account</h1>

          <!-- Form -->
          <form @submit.prevent="handleSignup" class="space-y-6">
            <!-- Full Name -->
            <div>
              <label class="block text-sm font-semibold text-gray-700 mb-2 uppercase">Full Name</label>
              <input
                v-model="formData.fullName"
                type="text"
                placeholder="Your name"
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500 focus:border-transparent"
                required
              />
            </div>

            <!-- Work Email -->
            <div>
              <label class="block text-sm font-semibold text-gray-700 mb-2 uppercase">Work Email</label>
              <input
                v-model="formData.email"
                type="email"
                placeholder="name@company.com"
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500 focus:border-transparent"
                required
              />
            </div>

            <!-- Password -->
            <div>
              <label class="block text-sm font-semibold text-gray-700 mb-2 uppercase">Password</label>
              <input
                v-model="formData.password"
                type="password"
                placeholder="8 or more alphanumeric and special characters"
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500 focus:border-transparent"
                required
              />
              <p class="text-xs text-gray-500 mt-2">8 or more alphanumeric and special characters</p>
            </div>

            <!-- Terms -->
            <div class="text-center text-sm text-gray-600">
              By signing up you agree to the
              <a href="#" class="text-green-600 hover:text-green-700 font-medium">Terms</a>
              and
              <a href="#" class="text-green-600 hover:text-green-700 font-medium">Privacy Policy</a>
            </div>

            <!-- Submit Button -->
            <button
              type="submit"
              class="w-full bg-green-600 text-white font-bold py-3 rounded-lg hover:bg-green-700 transition duration-200"
            >
              GET STARTED!
            </button>
          </form>

          <!-- Login Link -->
          <p class="text-center text-gray-600 mt-6">
            Already have an account?
            <NuxtLink to="/login" class="text-green-600 hover:text-green-700 font-semibold">Log in</NuxtLink>
          </p>
        </div>
      </div>
    </div>
  </Layout>
</template>

<script setup>
import Layout from '../../components/Layout.vue'
import { ref } from 'vue'

const formData = ref({ fullName: '', email: '', password: '' })
const handleSignup = () => {
  console.log('Signup data:', formData.value)
  alert('Account created successfully! (This is a demo)')
}
</script>

<style scoped>
</style>
