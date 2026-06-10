<template>
  <Layout>
  <div class="min-h-screen bg-white">
  

    <!-- Tab Navigation -->
    <div class="border-b border-gray-200">
      <div class="max-w-7xl mx-auto px-8">
        <div class="flex items-center gap-8 overflow-x-auto">
          <button
            v-for="tab in tabs"
            :key="tab.id"
            @click="activeTab = tab.id"
            :class="[
              'py-4 px-2 font-semibold text-sm whitespace-nowrap transition',
              activeTab === tab.id
                ? 'text-gray-900 border-b-2 border-gray-900'
                : 'text-gray-600 hover:text-gray-900'
            ]"
          >
            {{ tab.label }}
          </button>
        </div>
      </div>
    </div>

    <!-- Content Area -->
    <main class="max-w-7xl mx-auto px-8 py-16">
      <!-- Overview Tab Content -->
      <div v-show="activeTab === 'overview'" class="space-y-20">
        <!-- Enable Your App Section -->
        <section>
          <h2 class="text-4xl font-bold text-gray-900 text-center mb-16">Enable Your App with SMS in Minutes</h2>

          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Two-factor authentication -->
            <div class="p-6">
              <div class="flex items-start gap-4 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
                <h3 class="text-lg font-bold text-gray-900">Two-factor authentication</h3>
              </div>
              <p class="text-gray-600">Secure your applications at scale by sending dynamic verification codes.</p>
              <a href="#" class="text-green-600 hover:text-green-700 font-medium text-sm mt-4 inline-block">Learn more →</a>
            </div>

            <!-- Alerts and Notification -->
            <div class="p-6">
              <div class="flex items-start gap-4 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9" />
                </svg>
                <h3 class="text-lg font-bold text-gray-900">Alerts and Notifications</h3>
              </div>
              <p class="text-gray-600">Send automated account alerts, dispatch notifications or reminders.</p>
              <a href="#" class="text-green-600 hover:text-green-700 font-medium text-sm mt-4 inline-block">Learn more →</a>
            </div>

            <!-- SMS Marketing -->
            <div class="p-6">
              <div class="flex items-start gap-4 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M11 5.882V19.24a1.955 1.955 0 01-1.084-1.76V5.882m0 0h.933m-.933 0h.933m15.988 0a2.046 2.046 0 00-1.968-1.968h-6.96m0 0h.133a2.046 2.046 0 100 4.092h-6.87a2.047 2.047 0 00-2.047 2.047v10.787a2.047 2.047 0 002.047 2.047h6.942a2.047 2.047 0 002.047-2.047V8.414m0 0h.133a2.045 2.045 0 110 4.092-.963-.712" />
                </svg>
                <h3 class="text-lg font-bold text-gray-900">SMS Marketing and Publicity</h3>
              </div>
              <p class="text-gray-600">Engage with prospects and customers throughout their entire journey.</p>
              <a href="#" class="text-green-600 hover:text-green-700 font-medium text-sm mt-4 inline-block">Learn more →</a>
            </div>

            <!-- SMS Survey -->
            <div class="p-6">
              <div class="flex items-start gap-4 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2" />
                </svg>
                <h3 class="text-lg font-bold text-gray-900">SMS Survey</h3>
              </div>
              <p class="text-gray-600">Send and receive SMS, and conduct Surveys.</p>
              <a href="#" class="text-green-600 hover:text-green-700 font-medium text-sm mt-4 inline-block">Learn more →</a>
            </div>

            <!-- SMS Autoresponder -->
            <div class="p-6">
              <div class="flex items-start gap-4 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                </svg>
                <h3 class="text-lg font-bold text-gray-900">SMS Autoresponder</h3>
              </div>
              <p class="text-gray-600">Automatically respond to your customers while you are away.</p>
              <a href="#" class="text-green-600 hover:text-green-700 font-medium text-sm mt-4 inline-block">Learn more →</a>
            </div>

            <!-- Appointment Reminders -->
            <div class="p-6">
              <div class="flex items-start gap-4 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z" />
                </svg>
                <h3 class="text-lg font-bold text-gray-900">Appointment Reminders</h3>
              </div>
              <p class="text-gray-600">Reduce no-shows by sending automated reminder sms from your systems.</p>
              <a href="#" class="text-green-600 hover:text-green-700 font-medium text-sm mt-4 inline-block">Learn more →</a>
            </div>
          </div>
        </section>

        <!-- Global SMS Coverage -->
        <section class="py-16">
          <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
            <!-- Map -->
            <div class="relative">
              <svg class="w-full h-auto" viewBox="0 0 800 500" xmlns="http://www.w3.org/2000/svg">
                <!-- Simplified world map background -->
                <rect width="800" height="500" fill="#f0f5f9" />
                <!-- Map placeholder -->
                <text x="400" y="250" text-anchor="middle" font-size="24" fill="#ccc">World Map</text>
              </svg>
              <!-- Coverage badges positioned on map -->
              <div class="absolute top-1/4 left-1/3 transform -translate-x-1/2 -translate-y-1/2">
                <div class="w-12 h-12 bg-green-500 rounded-full flex items-center justify-center text-white font-bold text-sm">37</div>
              </div>
              <div class="absolute top-1/4 right-1/4 transform translate-x-1/2 -translate-y-1/2">
                <div class="w-12 h-12 bg-green-500 rounded-full flex items-center justify-center text-white font-bold text-sm">47</div>
              </div>
              <div class="absolute top-1/4 right-1/5 transform translate-x-1/2 -translate-y-1/2">
                <div class="w-12 h-12 bg-green-500 rounded-full flex items-center justify-center text-white font-bold text-sm">48</div>
              </div>
              <div class="absolute bottom-1/4 right-1/3 transform translate-x-1/2 translate-y-1/2">
                <div class="w-12 h-12 bg-green-500 rounded-full flex items-center justify-center text-white font-bold text-sm">55</div>
              </div>
              <div class="absolute bottom-1/4 left-1/4 transform -translate-x-1/2 translate-y-1/2">
                <div class="w-12 h-12 bg-green-500 rounded-full flex items-center justify-center text-white font-bold text-sm">13</div>
              </div>
              <div class="absolute bottom-1/3 right-1/6 transform translate-x-1/2 translate-y-1/2">
                <div class="w-12 h-12 bg-green-500 rounded-full flex items-center justify-center text-white font-bold text-sm">20</div>
              </div>
            </div>

            <!-- Coverage Info -->
            <div>
              <h2 class="text-4xl font-bold text-gray-900 mb-8">Global SMS Coverage</h2>
              <div class="space-y-4">
                <div class="flex items-start gap-3">
                  <svg class="w-6 h-6 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 20 20">
                    <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                  </svg>
                  <p class="text-gray-600">Over 190 Countries across North America, Europe, Asia, Oceania, South America and Africa</p>
                </div>
                <div class="flex items-start gap-3">
                  <svg class="w-6 h-6 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 20 20">
                    <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                  </svg>
                  <p class="text-gray-600">Receive incoming messages in 14 countries</p>
                </div>
                <div class="flex items-start gap-3">
                  <svg class="w-6 h-6 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 20 20">
                    <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                  </svg>
                  <p class="text-gray-600">Customize your sender ID in 100 countries outside of US & Canada</p>
                </div>
              </div>
              <button class="mt-8 px-6 py-3 bg-green-600 text-white font-semibold rounded hover:bg-green-700 transition">
                Explore Coverage
              </button>
            </div>
          </div>
        </section>

        <!-- Powerful Features Section -->
        <section class="py-16">
          <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-start">
            <div>
              <h2 class="text-4xl font-bold text-gray-900 mb-8">Powerful Features out of the Box</h2>
              <button class="px-6 py-3 bg-green-600 text-white font-semibold rounded hover:bg-green-700 transition">
                View All Features
              </button>
            </div>

            <div class="grid grid-cols-2 gap-6">
              <div class="flex items-start gap-3">
                <svg class="w-6 h-6 text-blue-400 flex-shrink-0" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                </svg>
                <p class="text-gray-900 font-medium">Long Message Concatenation</p>
              </div>
              <div class="flex items-start gap-3">
                <svg class="w-6 h-6 text-blue-400 flex-shrink-0" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                </svg>
                <p class="text-gray-900 font-medium">Handle opt out Intent</p>
              </div>
              <div class="flex items-start gap-3">
                <svg class="w-6 h-6 text-blue-400 flex-shrink-0" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                </svg>
                <p class="text-gray-900 font-medium">Support for any Character Set</p>
              </div>
              <div class="flex items-start gap-3">
                <svg class="w-6 h-6 text-blue-400 flex-shrink-0" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                </svg>
                <p class="text-gray-900 font-medium">Message Queuing</p>
              </div>
              <div class="flex items-start gap-3">
                <svg class="w-6 h-6 text-blue-400 flex-shrink-0" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                </svg>
                <p class="text-gray-900 font-medium">Default Message Body Purging</p>
              </div>
              <div class="flex items-start gap-3">
                <svg class="w-6 h-6 text-blue-400 flex-shrink-0" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                </svg>
                <p class="text-gray-900 font-medium">Number Pooling</p>
              </div>
              <div class="flex items-start gap-3">
                <svg class="w-6 h-6 text-blue-400 flex-shrink-0" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                </svg>
                <p class="text-gray-900 font-medium">Message Feedback API</p>
              </div>
              <div class="flex items-start gap-3">
                <svg class="w-6 h-6 text-blue-400 flex-shrink-0" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                </svg>
                <p class="text-gray-900 font-medium">Sticky Sender</p>
              </div>
            </div>
          </div>
        </section>

        <!-- More Ways Section -->
        <section class="py-16">
          <h2 class="text-4xl font-bold text-gray-900 text-center mb-16">More Ways to Send and Receive SMS<br />Around the World</h2>

          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
            <div>
              <div class="flex items-center justify-center w-12 h-12 bg-blue-100 rounded-full mb-4">
                <svg class="w-6 h-6 text-blue-600" fill="currentColor" viewBox="0 0 20 20">
                  <path d="M2 11a1 1 0 011-1h2a1 1 0 011 1v5a1 1 0 01-1 1H3a1 1 0 01-1-1v-5zM8 7a1 1 0 011-1h2a1 1 0 011 1v9a1 1 0 01-1 1H9a1 1 0 01-1-1V7zM14 4a1 1 0 011-1h2a1 1 0 011 1v12a1 1 0 01-1 1h-2a1 1 0 01-1-1V4z" />
                </svg>
              </div>
              <h3 class="font-bold text-gray-900 mb-2">Local Phone Numbers</h3>
              <p class="text-gray-600 text-sm">Use local or mobile phone numbers and send SMS to every country globally. Receive messages on SMS enabled phone numbers in 14 countries.</p>
            </div>

            <div>
              <div class="flex items-center justify-center w-12 h-12 bg-blue-100 rounded-full mb-4">
                <svg class="w-6 h-6 text-blue-600" fill="currentColor" viewBox="0 0 20 20">
                  <path d="M2 5a2 2 0 012-2h12a2 2 0 012 2v10a2 2 0 01-2 2H4a2 2 0 01-2-2V5z" />
                </svg>
              </div>
              <h3 class="font-bold text-gray-900 mb-2">Alphanumeric Sender ID</h3>
              <p class="text-gray-600 text-sm">Customize your sender ID to your brand by using alphanumeric characters for your outbound messages in 100 countries outside of US & Canada.</p>
            </div>

            <div>
              <div class="flex items-center justify-center w-12 h-12 bg-blue-100 rounded-full mb-4">
                <svg class="w-6 h-6 text-blue-600" fill="currentColor" viewBox="0 0 20 20">
                  <path d="M2 3a1 1 0 011-1h2.153a1 1 0 01.986.836l.74 4.435a1 1 0 01-.54 1.06l-1.548.773c.058.319.105.635.105.954 0 5.338 3.851 9.853 8.979 10.476.29.023.579.023.869 0l1.83-2.034c.27-.3.656-.383 1.011-.235l4.332 2.166a1 1 0 01.572 1.32l-.867 2.6A1 1 0 0120 20c-11.046 0-20-8.954-20-20a1 1 0 01.732-.984l2.6-.867z" />
                </svg>
              </div>
              <h3 class="font-bold text-gray-900 mb-2">Toll free Numbers</h3>
              <p class="text-gray-600 text-sm">Send and receive SMS using Toll-free numbers in US & Canada. Buy a new number or enable your existing number to send and receive SMS.</p>
            </div>

            <div>
              <div class="flex items-center justify-center w-12 h-12 bg-blue-100 rounded-full mb-4">
                <svg class="w-6 h-6 text-blue-600" fill="currentColor" viewBox="0 0 20 20">
                  <path d="M5 3a2 2 0 00-2 2v6h6V5a2 2 0 00-2-2H5zm6 0a2 2 0 00-2 2v6h6V5a2 2 0 00-2-2h-2z" />
                </svg>
              </div>
              <h3 class="font-bold text-gray-900 mb-2">Short Code</h3>
              <p class="text-gray-600 text-sm">Send and receive high throughput and large volume of SMS using Short Codes in the U.S and Canada.</p>
              <a href="#" class="text-green-600 hover:text-green-700 font-medium text-sm inline-block mt-3">Learn More →</a>
            </div>
          </div>
        </section>

        <!-- Reasons Why Section -->
        <section class="py-16">
          <h2 class="text-4xl font-bold text-gray-900 text-center mb-16">Top reasons why businesses choose Plivo</h2>

          <div class="grid grid-cols-1 md:grid-cols-2 gap-12">
            <div class="flex items-start gap-6">
              <svg class="w-12 h-12 text-green-500 flex-shrink-0" fill="currentColor" viewBox="0 0 24 24">
                <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2z" />
              </svg>
              <div>
                <h3 class="text-xl font-bold text-gray-900 mb-2">Proven Quality and Scale</h3>
                <p class="text-gray-600">With over a billion API requests every month, our globally distributed direct to carrier network and intelligent routing ensures highest SMS delivery and lowest latency for your calls.</p>
              </div>
            </div>

            <div class="flex items-start gap-6">
              <svg class="w-12 h-12 text-green-500 flex-shrink-0" fill="currentColor" viewBox="0 0 24 24">
                <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
              </svg>
              <div>
                <h3 class="text-xl font-bold text-gray-900 mb-2">Enterprise Grade Platform</h3>
                <p class="text-gray-600">Engineered for high availability, extreme reliability and 99.95% uptime SLA. Privacy Shield and GDPR Compliance means any business can trust Plivo with data privacy and security.</p>
              </div>
            </div>

            <div class="flex items-start gap-6">
              <svg class="w-12 h-12 text-green-500 flex-shrink-0" fill="currentColor" viewBox="0 0 24 24">
                <path d="M18 9v3m0 0v3m0-3h3m-3 0h-3m-2-5a4 4 0 11-8 0 4 4 0 018 0zM3 20a6 6 0 0112 0v1H3v-1z" />
              </svg>
              <div>
                <h3 class="text-xl font-bold text-gray-900 mb-2">A Team That Truly Cares about Your Success</h3>
                <p class="text-gray-600">Our 24x7 premium support and a consultative customer success team, provide you with all the technical guidance and industry expertise you need, when you need it.</p>
              </div>
            </div>

            <div class="flex items-start gap-6">
              <svg class="w-12 h-12 text-green-500 flex-shrink-0" fill="currentColor" viewBox="0 0 24 24">
                <path d="M12 8c-1.657 0-3 .895-3 2s1.343 2 3 2 3 .895 3 2-1.343 2-3 2m0-8c1.11 0 2.08.402 2.599 1M12 8V7m0 1v8m0 0v1m0-1c-1.11 0-2.08-.402-2.599-1M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
              </svg>
              <div>
                <h3 class="text-xl font-bold text-gray-900 mb-2">Lower Cost of Ownership</h3>
                <p class="text-gray-600">Receive discounted pricing from the start with simple usage based pricing where you only pay for what you use. Avail additional discounts with committed usage as you scale.</p>
              </div>
            </div>
          </div>
        </section>
      </div>

      <!-- Features Tab Content -->
      <div v-show="activeTab === 'features'" class="space-y-20">
        <!-- Hero Section -->
        <section class="text-center py-16">
          <h2 class="text-5xl font-bold text-gray-900 mb-4">Features - SMS API Platform</h2>
          <p class="text-xl text-gray-600 mb-8">Powerful SMS functionality for your applications at a global scale</p>
          <div class="flex items-center justify-center gap-4">
            <button class="px-8 py-3 bg-blue-900 text-white font-bold rounded hover:bg-blue-800 transition">
              GET STARTED NOW
            </button>
            <button class="px-8 py-3 border-2 border-gray-900 text-gray-900 font-bold rounded hover:bg-gray-900 hover:text-white transition">
              TALK TO AN EXPERT
            </button>
          </div>
        </section>

        <!-- Essentials Section -->
        <section>
          <div class="flex items-start gap-4 mb-12">
            <h2 class="text-3xl font-bold text-gray-900">Essentials</h2>
            <div class="w-1 h-8 bg-gray-300"></div>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Essential features -->
            <div class="col-span-1">
              <p class="text-gray-600 leading-relaxed">Essential features already built for you so you can focus on integrating SMS in your application & scale your delivery globally.</p>
            </div>

            <!-- Support for any character set -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <text x="50%" y="50%" dominant-baseline="middle" text-anchor="middle" font-size="16" fill="currentColor">aa</text>
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Support for any character set</h3>
              <p class="text-gray-600">Built in GSM & Unicode character set support to allow any language including Chinese, Arabic and others plus emojis & symbols.</p>
            </div>

            <!-- Long Message Concatenation -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M4 6h16M4 12h16M4 18h16" stroke="currentColor" stroke-width="2" fill="none"/>
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Long Message Concatenation</h3>
              <p class="text-gray-600">No more split messages. Long messages are automatically concatenated across global networks seamlessly.</p>
            </div>

            <!-- Delivery Report Notifications -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Delivery Report Notifications</h3>
              <p class="text-gray-600">Receive real-time delivery notification of messages sent globally. Track delivery rates and performance of your accounts.</p>
            </div>

            <!-- Message Queuing -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M4 6h16M4 12h16M4 18h16" stroke="currentColor" stroke-width="2" fill="none"/>
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Message Queuing</h3>
              <p class="text-gray-600">Send multiple SMS in a single API request. We handle the message queuing for you so you don't have to worry about building that.</p>
            </div>

            <!-- MMS Rich-media Support -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M4 16l4.586-4.586a2 2 0 012.828 0L16 16m-2-2l1.586-1.586a2 2 0 012.828 0L20 14m-6-6h.01M6 20h12a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2z" />
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">MMS Rich-media Support</h3>
              <p class="text-gray-600">Send and receive photos, gifs, videos and more. Support to send and receive picture messages and SMS in the same phone number.</p>
              <a href="#" class="text-green-600 hover:text-green-700 font-medium text-sm mt-4 inline-block">Learn More →</a>
            </div>
          </div>
        </section>

        <!-- Compliance Section -->
        <section>
          <div class="flex items-start gap-4 mb-12">
            <h2 class="text-3xl font-bold text-gray-900">Compliance</h2>
            <div class="w-1 h-8 bg-gray-300"></div>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Compliance intro -->
            <div class="col-span-1">
              <p class="text-gray-600 leading-relaxed">Built in local, regulatory and data compliance which frees you up to build your application at scale.</p>
            </div>

            <!-- Message Body Purging -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Message Body Purging</h3>
              <p class="text-gray-600">SMS message content is never stored within any message detail record. By default all debug logs are purged after 30 days.</p>
            </div>

            <!-- Protect Sensitive Data -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Protect Sensitive Data</h3>
              <p class="text-gray-600">Hospitals and other regulated industries use Plivo globally. Disable logging and mask phone numbers to protect for such use cases.</p>
            </div>

            <!-- Smart Rate Limiting -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Smart Rate Limiting</h3>
              <p class="text-gray-600">Stay compliant with messaging frequency and throughput regulations per source number in each country.</p>
            </div>

            <!-- Automatic Opt-out Handling -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Automatic Opt-out Handling</h3>
              <p class="text-gray-600">Replies such as "Stop", "Cancel" are automatically handled for you on long codes. Plivo manages the opt-outs in such cases.</p>
            </div>
          </div>
        </section>

        <!-- Improved Message Delivery Section -->
        <section>
          <div class="flex items-start gap-4 mb-12">
            <h2 class="text-3xl font-bold text-gray-900">Improved<br/>Message Delivery</h2>
            <div class="w-1 h-8 bg-gray-300"></div>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Delivery intro -->
            <div class="col-span-1">
              <p class="text-gray-600 leading-relaxed">Quality based routing engine and other features to ensure the best deliverability across 200 countries.</p>
            </div>

            <!-- Intelligent Message Encoding -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M4 6h16M4 12h16M4 18h16" stroke="currentColor" stroke-width="2" fill="none"/>
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Intelligent Message Encoding</h3>
              <p class="text-gray-600">Plivo replaces unicode characters with similar gsm characters to ensure message delivery to destination networks that don't support unicode.</p>
            </div>

            <!-- Number Pooling -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M4 6h16M4 12h16M4 18h16" stroke="currentColor" stroke-width="2" fill="none"/>
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Number Pooling</h3>
              <p class="text-gray-600">Improve delivery rate by spreading your messages across a pool of phone numbers to reach your users in time.</p>
            </div>

            <!-- Conversion API -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Conversion API</h3>
              <p class="text-gray-600">Real time feedback from your application allows Plivo's self adjusting quality based routing engine to ensures best delivery.</p>
            </div>

            <!-- Local Match -->
            <div>
              <div class="flex items-start gap-3 mb-4">
                <svg class="w-8 h-8 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
              </div>
              <h3 class="text-lg font-bold text-gray-900 mb-2">Local Match</h3>
              <p class="text-gray-600">To improve read rates, auto select a local area number as the sender id for each user from a pool of numbers.</p>
            </div>
          </div>
        </section>

        <!-- Faster Time to Market Section -->
        <section class="py-16">
          <h2 class="text-4xl font-bold text-gray-900 text-center mb-4">Faster Time to Market</h2>
          <p class="text-center text-gray-600 max-w-3xl mx-auto mb-16">Build, Integrate and troubleshoot issues faster. With Plivo focus on building the features that differentiates you and be faster to the market.</p>

          <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-start">
            <!-- Left side - Features list -->
            <div class="space-y-6">
              <div class="flex items-start gap-4">
                <svg class="w-6 h-6 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                </svg>
                <div>
                  <h3 class="text-lg font-bold text-gray-900 mb-1">Sticky Sender</h3>
                  <p class="text-gray-600">Interact with customers using the same recognizable phone number or sender ID to ensure a better experience.</p>
                </div>
              </div>

              <div class="flex items-start gap-4">
                <svg class="w-6 h-6 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                </svg>
                <div>
                  <h3 class="text-lg font-bold text-gray-900 mb-1">Built in Multi-tenancy</h3>
                  <p class="text-gray-600">Segment your customers based on use case, spend capacity or risk profile and track usage and billing with Sub-Accounts.</p>
                </div>
              </div>

              <div class="flex items-start gap-4">
                <svg class="w-6 h-6 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                </svg>
                <div>
                  <h3 class="text-lg font-bold text-gray-900 mb-1">Detailed Debug Logs</h3>
                  <p class="text-gray-600">Debug and troubleshoot issues and problems faster with detailed logs. Drill down to the details to find the root cause.</p>
                </div>
              </div>
            </div>

            <!-- Right side - Illustration and more features -->
            <div class="space-y-6">
              <div class="bg-gradient-to-br from-blue-50 to-blue-100 rounded-lg p-8 h-64 flex items-center justify-center">
                <p class="text-gray-500 text-center">Developer Tools Illustration</p>
              </div>

              <div class="flex items-start gap-4">
                <svg class="w-6 h-6 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                </svg>
                <div>
                  <h3 class="text-lg font-bold text-gray-900 mb-1">Extensive Documentation</h3>
                  <p class="text-gray-600">With our detailed documentation and sample code get started in minutes. Just copy paste code samples in most cases.</p>
                </div>
              </div>

              <div class="flex items-start gap-4">
                <svg class="w-6 h-6 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                </svg>
                <div>
                  <h3 class="text-lg font-bold text-gray-900 mb-1">Server Side SDKs</h3>
                  <p class="text-gray-600">Program in your web language of choice with our server side SDKs in Java, C#, Python, Ruby, Nodejs or Golang.</p>
                </div>
              </div>

              <div class="flex items-start gap-4">
                <svg class="w-6 h-6 text-blue-400 flex-shrink-0 mt-1" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                </svg>
                <div>
                  <h3 class="text-lg font-bold text-gray-900 mb-1">Reusable Templates</h3>
                  <p class="text-gray-600">With a vast library of ready to use templates you can add powerful functionality quickly by writing minimal code.</p>
                </div>
              </div>
            </div>
          </div>
        </section>

        <!-- CTA Section -->
        <section class="text-center py-16">
          <h2 class="text-4xl font-bold text-gray-900 mb-4">It's easy to get started. Sign up for free.</h2>
          <p class="text-gray-600 mb-8">Create your account and receive trial credits or get in touch with us</p>
          <div class="flex items-center justify-center gap-4">
            <button class="px-8 py-3 bg-green-600 text-white font-bold rounded hover:bg-green-700 transition">
              GET STARTED NOW
            </button>
            <button class="px-8 py-3 border-2 border-green-600 text-green-600 font-bold rounded hover:bg-green-600 hover:text-white transition">
              TALK TO AN EXPERT
            </button>
          </div>
        </section>
      </div>
    </main>

    <!-- Footer -->
    <footer class="bg-gray-50 border-t border-gray-200 mt-20">
      <div class="max-w-7xl mx-auto px-8 py-12">
        <p class="text-center text-gray-600">© 2024 Plivo. All rights reserved.</p>
      </div>
    </footer>
  </div>

</Layout>
</template>

<script setup>
import { ref } from 'vue'

const activeTab = ref('overview')

const tabs = [
  { id: 'overview', label: 'OVERVIEW' },
  { id: 'features', label: 'FEATURES' },
  { id: 'coverage', label: 'COVERAGE' },
  { id: 'shortcode', label: 'SHORT CODE' },
  { id: 'tollfree', label: 'TOLL-FREE' },
  { id: 'mms', label: 'MMS' },
  { id: 'powerpack', label: 'POWERPACK' },
  { id: 'pricing', label: 'PRICING' }
]
</script>

<style scoped>
button {
  transition: all 0.2s ease;
}
</style>