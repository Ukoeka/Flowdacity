<template>
  <Layout>
    <!-- Hero Section -->
    <section class="bg-white py-20 px-8">
      <div class="max-w-7xl mx-auto grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
        <!-- Left Content -->
        <div>
          <div class="inline-block bg-green-100 text-green-700 px-3 py-1 rounded-full text-sm font-medium mb-6">
            🆕 Zentrunk - A Modern Approach to SIP Trunking →
          </div>

          <h1 class="text-5xl lg:text-6xl font-bold text-gray-900 mb-6 leading-tight">
            Connect and engage with your customers globally
          </h1>
          <p class="text-lg text-gray-600 mb-8">
            Flowdacity's voice and messaging platform enables businesses to create and deliver better customer experiences.
          </p>

          <div class="flex gap-4">
            <button class="px-8 py-3 bg-blue-900 text-white font-bold rounded hover:bg-blue-800 transition">
              GET STARTED NOW
            </button>
            <button class="px-8 py-3 border-2 border-gray-900 text-gray-900 font-bold rounded hover:bg-gray-900 hover:text-white transition">
              TALK TO AN EXPERT
            </button>
          </div>
        </div>

        <!-- Right Illustration -->
        <div class="relative h-96 lg:h-full">
          <div class="grid grid-cols-2 gap-4 h-full">
            <div class="bg-gradient-to-br from-blue-100 to-blue-50 rounded-lg p-6 flex items-center justify-center">
              <div class="text-center">
                <div class="text-4xl mb-2">📱</div>
                <p class="text-sm text-gray-600">SMS & Voice</p>
              </div>
            </div>
            <div class="bg-gradient-to-br from-purple-100 to-purple-50 rounded-lg p-6 flex items-center justify-center">
              <div class="text-center">
                <div class="text-4xl mb-2">👥</div>
                <p class="text-sm text-gray-600">Global Reach</p>
              </div>
            </div>
            <div class="bg-gradient-to-br from-green-100 to-green-50 rounded-lg p-6 flex items-center justify-center">
              <div class="text-center">
                <div class="text-4xl mb-2">⚡</div>
                <p class="text-sm text-gray-600">Real-time API</p>
              </div>
            </div>
            <div class="bg-gradient-to-br from-yellow-100 to-yellow-50 rounded-lg p-6 flex items-center justify-center">
              <div class="text-center">
                <div class="text-4xl mb-2">🔐</div>
                <p class="text-sm text-gray-600">Enterprise Grade</p>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Companies -->
      <div class="max-w-7xl mx-auto mt-20">
        <p class="text-center text-gray-600 mb-8">Trusted by leading companies worldwide</p>
        <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-8 gap-8 items-center justify-center">
          <div class="text-gray-400 font-bold">IBM</div>
          <div class="text-gray-400 font-bold">GoDaddy</div>
          <div class="text-gray-400 font-bold">SnapCall</div>
          <div class="text-gray-400 font-bold">Grayblind</div>
          <div class="text-gray-400 font-bold">OLA</div>
          <div class="text-gray-400 font-bold">GOJEK</div>
          <div class="text-gray-400 font-bold">PagerDuty</div>
          <div class="text-gray-400 font-bold">Lifesize</div>
        </div>
        <p class="text-center text-green-600 mt-8 text-sm">
          Learn how thousands of innovative businesses rely on Flowdacity for their customer engagement. →
        </p>
      </div>
    </section>

    <!-- Enterprise Section -->
    <section class="bg-gray-50 py-16 px-8 text-center">
      <h2 class="text-4xl font-bold text-gray-900 mb-4">
        Enterprise grade communications stack for your business
      </h2>
    </section>

    <!-- Products Section -->
    <section class="bg-white py-16 px-8">
      <div class="max-w-7xl mx-auto">
        <!-- PHLO Card -->
        <div class="bg-gray-50 p-8 rounded-lg mb-8 flex items-center justify-between">
          <div class="flex items-center gap-4">
            <div class="w-12 h-12 bg-blue-100 rounded flex items-center justify-center">
              <span class="text-2xl">📋</span>
            </div>
            <div>
              <h3 class="text-xl font-bold text-gray-900">PHLO</h3>
              <p class="text-gray-600">Drag. Drop. Deploy to manage your communication workflows visually</p>
            </div>
          </div>
          <a href="#" class="text-green-600 font-medium hover:underline">Learn More →</a>
        </div>

        <!-- Products Grid -->
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-16">
          <!-- SMS API -->
          <div class="border border-gray-200 rounded-lg p-8">
            <div class="flex items-center gap-3 mb-4">
              <span class="text-3xl">💬</span>
              <h3 class="text-xl font-bold text-gray-900">SMS API Platform</h3>
            </div>
            <p class="text-gray-600 mb-6">
              Programmatically send and receive text messages in over 190 countries globally.
            </p>
            <a href="#" class="text-green-600 font-medium hover:underline">Learn More →</a>
          </div>

          <!-- Voice API -->
          <div class="border border-gray-200 rounded-lg p-8">
            <div class="flex items-center gap-3 mb-4">
              <span class="text-3xl">📞</span>
              <h3 class="text-xl font-bold text-gray-900">Voice API Platform</h3>
            </div>
            <p class="text-gray-600 mb-6">
              Integrate powerful voice calling functionality within your apps programmatically.
            </p>
            <a href="#" class="text-green-600 font-medium hover:underline">Learn More →</a>
          </div>

          <!-- Zentrunk -->
          <div class="border border-gray-200 rounded-lg p-8">
            <div class="flex items-center gap-3 mb-4">
              <span class="text-3xl">☎️</span>
              <div>
                <h3 class="text-xl font-bold text-gray-900">Zentrunk</h3>
                <span class="text-xs bg-green-100 text-green-700 px-2 py-1 rounded">NEW</span>
              </div>
            </div>
            <p class="text-gray-600 mb-6">
              Cloud based SIP Trunking to make and receive calls with your VoIP infrastructure.
            </p>
            <a href="#" class="text-green-600 font-medium hover:underline">Learn More →</a>
          </div>

          <!-- Phone Numbers -->
          <div class="border border-gray-200 rounded-lg p-8">
            <div class="flex items-center gap-3 mb-4">
              <span class="text-3xl">🔢</span>
              <h3 class="text-xl font-bold text-gray-900 mb-4">Phone Numbers</h3>
            </div>
            <p class="text-gray-600 mb-6">
              Search and buy local, mobile, and toll-free numbers for your business worldwide.
            </p>
            <a href="#" class="text-green-600 font-medium hover:underline">Learn More →</a>
          </div>
        </div>
      </div>
    </section>

    <!-- Solutions Templates -->
    <section class="bg-gray-50 py-16 px-8">
      <div class="max-w-7xl mx-auto">
        <h2 class="text-4xl font-bold text-center text-gray-900 mb-12">Explore our solutions templates</h2>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <!-- Two-factor Authentication -->
          <div class="bg-white rounded-lg p-8">
            <div class="text-4xl mb-4">✓</div>
            <h3 class="text-xl font-bold text-gray-900 mb-4">Two-factor Authentication</h3>
            <p class="text-gray-600 mb-6">
              Secure your applications by authenticating via dynamic verification codes.
            </p>
            <a href="#" class="text-green-600 font-medium hover:underline">Learn More →</a>
          </div>

          <!-- Call Tracking -->
          <div class="bg-white rounded-lg p-8">
            <div class="text-4xl mb-4">📊</div>
            <h3 class="text-xl font-bold text-gray-900 mb-4">Call Tracking</h3>
            <p class="text-gray-600 mb-6">
              Measure and track the effectiveness of your online and offline ad campaigns.
            </p>
            <a href="#" class="text-green-600 font-medium hover:underline">Learn More →</a>
          </div>

          <!-- Alerts and Notifications -->
          <div class="bg-white rounded-lg p-8">
            <div class="text-4xl mb-4">🔔</div>
            <h3 class="text-xl font-bold text-gray-900 mb-4">Alerts and Notifications</h3>
            <p class="text-gray-600 mb-6">
              Send account alerts, dispatch notifications or custom reminders.
            </p>
            <a href="#" class="text-green-600 font-medium hover:underline">Learn More →</a>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="bg-white py-20 px-8 text-center">
      <div class="max-w-3xl mx-auto">
        <h2 class="text-4xl font-bold text-gray-900 mb-6">It's easy to get started. Sign up for free.</h2>
        <p class="text-lg text-gray-600 mb-8">
          Create your account and receive trial credits or get in touch with us
        </p>

        <div class="flex flex-col sm:flex-row gap-4 justify-center">
          <button class="px-8 py-3 bg-green-600 text-white font-bold rounded hover:bg-green-700 transition">
            GET STARTED NOW
          </button>
          <button class="px-8 py-3 border-2 border-green-600 text-green-600 font-bold rounded hover:bg-green-600 hover:text-white transition">
            TALK TO AN EXPERT
          </button>
        </div>
      </div>
    </section>
  </Layout>
</template>

<script setup>
import Layout from '../components/Layout.vue'
</script>

<style scoped>
</style>