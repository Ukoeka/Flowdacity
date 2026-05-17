<template>
 <Layout>
     <div class="bg-white">
    <!-- Header with Logo -->
    

    <!-- Hero Section -->
    <section class="py-20 px-8 text-center relative overflow-hidden">
      <!-- Decorative dots -->
      <div class="absolute top-10 left-1/2 transform -translate-x-1/2 w-32 h-32 opacity-10">
        <div class="grid grid-cols-6 gap-2">
          <div v-for="i in 24" :key="i" class="w-1 h-1 bg-gray-400 rounded-full"></div>
        </div>
      </div>

      <div class="max-w-3xl mx-auto relative z-10">
        <h1 class="text-5xl font-bold text-blue-900 mb-6">Flowdacity Pricing</h1>
        <p class="text-lg text-gray-600 mb-2">
          Start with our competitive pay as you go pricing. For deeper discounts on
        </p>
        <p class="text-lg text-gray-600">
          committed spend as you scale,
          <a href="#" class="text-green-600 hover:text-green-700 font-semibold">talk with our sales team.</a>
        </p>
      </div>

      <!-- Country Selector -->
      <div class="max-w-3xl mx-auto mt-12">
        <div class="inline-block w-full sm:w-80">
          <div class="flex items-center gap-3 px-6 py-3 border border-gray-300 rounded-lg bg-white hover:border-gray-400 cursor-pointer">
            <span class="text-2xl">🇺🇸</span>
            <span class="text-gray-700 font-medium">United States</span>
            <span class="ml-auto">▼</span>
          </div>
        </div>
      </div>
    </section>

    <!-- Pricing Cards Section -->
    <section class="py-20 px-8 bg-gray-50">
      <div class="max-w-7xl mx-auto">
        <!-- SMS API Platform & Voice API Platform -->
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 mb-8">
          <!-- SMS API Platform -->
          <div class="bg-white rounded-lg p-8 shadow-sm">
            <div class="flex items-center gap-3 mb-8">
              <span class="text-3xl">💬</span>
              <h3 class="text-2xl font-bold text-gray-900">SMS API Platform</h3>
            </div>

            <div class="space-y-8 flex flex-col">
              <!-- Send SMS -->
             <div class="flex justify-between items-center">
                 <div>
                <p class="text-sm font-semibold text-gray-600 uppercase mb-2">TO SEND AN SMS</p>
                <p class="text-4xl font-bold text-gray-900">
                  <span class="text-2xl">$</span>0.0050<span class="text-lg">/sms</span>
                </p>
              </div>

              <div>
                <p class="text-sm font-semibold text-gray-600 uppercase mb-2">TO RECEIVE AN SMS</p>
                <p class="text-4xl font-bold text-gray-900">
                  <span class="text-2xl">$</span>0.0000<span class="text-lg">/sms</span>
                </p>
              </div>
             </div>

              <button class="w-full border-2 border-green-600 text-green-600 font-bold py-3 rounded hover:bg-green-50 transition uppercase">
                VIEW DETAILED PRICING
              </button>
            </div>
          </div>

          <!-- Voice API Platform -->
          <div class="bg-white rounded-lg p-8 shadow-sm">
            <div class="flex items-center gap-3 mb-8">
              <span class="text-3xl">📞</span>
              <h3 class="text-2xl font-bold text-gray-900">Voice API Platform</h3>
            </div>

            <div class="space-y-8">
              <div class="flex justify-between items-center">
                <div>
                <p class="text-sm font-semibold text-gray-600 uppercase mb-2">TO MAKE A CALL</p>
                <p class="text-sm text-gray-500 mb-1">Starts at</p>
                <p class="text-4xl font-bold text-gray-900">
                  <span class="text-2xl">$</span>0.0120<span class="text-lg">/min</span>
                </p>
              </div>

              <!-- Receive Call -->
              <div>
                <p class="text-sm font-semibold text-gray-600 uppercase mb-2">TO RECEIVE A CALL</p>
                <p class="text-4xl font-bold text-gray-900">
                  <span class="text-2xl">$</span>0.0085<span class="text-lg">/min</span>
                </p>
              </div>
              </div>

              <button class="w-full border-2 border-green-600 text-green-600 font-bold py-3 rounded hover:bg-green-50 transition uppercase">
                VIEW DETAILED PRICING
              </button>
            </div>
          </div>
        </div>

        <!-- Zentrunk & Phone Numbers -->
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
          <!-- Zentrunk -->
          <div class="bg-white rounded-lg p-8 shadow-sm">
            <div class="flex items-center gap-3 mb-8">
              <span class="text-3xl">☎️</span>
              <h3 class="text-2xl font-bold text-gray-900">Zentrunk - SIP Trunking</h3>
            </div>

            <div class="space-y-6">
              <div class="flex justify-between items-center">
                <!-- Make Call -->
              <div>
                <p class="text-sm font-semibold text-gray-600 uppercase mb-2">TO MAKE A CALL</p>
                <p class="text-sm text-gray-500 mb-1">Starts at</p>
                <p class="text-4xl font-bold text-gray-900">
                  <span class="text-2xl">$</span>0.0065<span class="text-lg">/min</span>
                </p>
              </div>

              <!-- Receive Call -->
              <div>
                <p class="text-sm font-semibold text-gray-600 uppercase mb-2">TO RECEIVE A CALL</p>
                <p class="text-4xl font-bold text-gray-900">
                  <span class="text-2xl">$</span>0.0025<span class="text-lg">/min</span>
                </p>
              </div>
              </div>

              <button class="w-full border-2 border-green-600 text-green-600 font-bold py-3 rounded hover:bg-green-50 transition uppercase">
                VIEW DETAILED PRICING
              </button>
            </div>
          </div>

          <!-- Phone Numbers -->
          <div class="bg-white rounded-lg p-8 shadow-sm">
            <div class="flex items-center gap-3 mb-8">
              <span class="text-3xl">🔢</span>
              <h3 class="text-2xl font-bold text-gray-900">Phone Numbers</h3>
            </div>

            <div class="space-y-6">
              <!-- Local Numbers -->
              <div class="flex justify-between items-center">
                <div>
                <p class="text-sm font-semibold text-gray-600 uppercase mb-2">LOCAL NUMBERS</p>
                <p class="text-4xl font-bold text-gray-900">
                  <span class="text-2xl">$</span>0.80<span class="text-lg">/month</span>
                </p>
              </div>

              <!-- Toll Free Numbers -->
              <div>
                <p class="text-sm font-semibold text-gray-600 uppercase mb-2">TOLL FREE NUMBERS</p>
                <p class="text-4xl font-bold text-gray-900">
                  <span class="text-2xl">$</span>1.00<span class="text-lg">/month</span>
                </p>
              </div>

              <!-- Short Code -->
              <div>
                <p class="text-sm font-semibold text-gray-600 uppercase mb-2">SHORT CODE</p>
                <p class="text-sm text-gray-500 mb-1">Starts at</p>
                <p class="text-4xl font-bold text-gray-900">
                  <span class="text-2xl">$</span>500<span class="text-lg">/month</span>
                </p>
              </div>
              </div>

              <button class="w-full border-2 border-green-600 text-green-600 font-bold py-3 rounded hover:bg-green-50 transition uppercase">
                VIEW DETAILED PRICING
              </button>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Committed Spend Discounts -->
    <section class="py-20 px-8 bg-white">
      <div class="max-w-3xl mx-auto text-center">
        <h2 class="text-4xl font-bold text-blue-900 mb-4">Committed Spend Discounts</h2>
        <p class="text-lg text-gray-600 mb-8">
          Avail deeper volume discounts on committed spends as you scale your usage.
        </p>
        <button class="px-8 py-3 bg-green-600 text-white font-bold rounded hover:bg-green-700 transition uppercase">
          CONTACT SALES
        </button>
      </div>
    </section>

    <!-- Testimonials -->
    <section class="py-20 px-8 bg-gray-50">
      <div class="max-w-7xl mx-auto">
        <h2 class="text-4xl font-bold text-center text-blue-900 mb-12">What Our Customers Are Saying!</h2>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <!-- Testimonial 1 -->
          <div class="bg-white rounded-lg p-8 shadow-sm">
            <p class="text-gray-600 mb-6 leading-relaxed">
              "I could tell from the get-go that Plivo was going to offer outstanding service."
            </p>
            <div>
              <p class="font-bold text-gray-900">DECKERS</p>
              <p class="font-bold text-gray-900">BRANDS</p>
              <p class="text-sm text-gray-600 mt-2">Jacob Martinez, Associated Project Manager</p>
            </div>
          </div>

          <!-- Testimonial 2 -->
          <div class="bg-white rounded-lg p-8 shadow-sm">
            <p class="text-gray-600 mb-6 leading-relaxed">
              "The core of our workflow is Plivo's webhook on incoming calls, adding some metadata on our end, and then redirecting. It was just so easy to implement, and made Plivo a clear winner over any other competition."
            </p>
            <div>
              <p class="font-bold text-gray-900">HOUST</p>
              <p class="text-sm text-gray-600 mt-2">Matuszkiewicz, Engineering Manager</p>
            </div>
          </div>

          <!-- Testimonial 3 -->
          <div class="bg-white rounded-lg p-8 shadow-sm">
            <p class="text-gray-600 mb-6 leading-relaxed">
              "The service reports are very informative. The check-ins let us know that we're a valued partner, and that really makes us feel good about our decision to use Plivo."
            </p>
            <div>
              <p class="font-bold text-gray-900">GUESTFM</p>
              <p class="text-sm text-gray-600 mt-2">Scot Cromer, CEO</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- FAQ Section -->
    <section class="py-20 px-8 bg-white">
      <div class="max-w-7xl mx-auto">
        <h2 class="text-4xl font-bold text-center text-blue-900 mb-12">Frequently Asked Questions</h2>
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12">
          <div class="space-y-8">
            <details class="border rounded-lg p-4 bg-white shadow-sm">
              <summary class="font-semibold text-gray-900 cursor-pointer">Can I try Plivo's products for free?</summary>
              <p class="text-gray-600 mt-2">Yes, we do provide free credits for you to try our products. <a href="#" class="text-green-600 font-semibold">Sign up</a> with your work email to redeem your free credits and build your application.</p>
            </details>
            <details class="border rounded-lg p-4 bg-white shadow-sm">
              <summary class="font-semibold text-gray-900 cursor-pointer">Do you have example applications built using Plivo?</summary>
              <p class="text-gray-600 mt-2">Check out our <a href="#" class="text-green-600 hover:text-green-700 font-semibold">developer docs</a> for example applications in various different languages. If you need any further help check out our detailed <a href="#" class="text-green-600 hover:text-green-700 font-semibold">knowledgebase</a>.</p>
            </details>
            <details class="border rounded-lg p-4 bg-white shadow-sm">
              <summary class="font-semibold text-gray-900 cursor-pointer">How do I estimate monthly spend for my volume?</summary>
              <p class="text-gray-600 mt-2">We are happy to help you estimate your monthly spend based on your volumes and use case. <a href="#" class="text-green-600 font-semibold">Contact our sales team</a> to understand the details of how pricing would work for your use case.</p>
            </details>
          </div>
          <div class="space-y-8">
            <details class="border rounded-lg p-4 bg-white shadow-sm">
              <summary class="font-semibold text-gray-900 cursor-pointer">Can I try more than one product at the same time?</summary>
              <p class="text-gray-600 mt-2">Yes, you are more than welcome to try any combination of products for your use case or needs.</p>
            </details>
            <details class="border rounded-lg p-4 bg-white shadow-sm">
              <summary class="font-semibold text-gray-900 cursor-pointer">How does pricing work for SMS and Phone Calls?</summary>
              <p class="text-gray-600 mt-2">Each SMS is charged per unit sent or received. Voice Calls are charged per minute for each call made or received. Phone Numbers are charged a monthly rental fee at the start of the month.</p>
            </details>
            <details class="border rounded-lg p-4 bg-white shadow-sm">
              <summary class="font-semibold text-gray-900 cursor-pointer">Is my data safe with Plivo?</summary>
              <p class="text-gray-600 mt-2">We take data security and privacy as our top priority. As an example, we are compliant with GDPR, CCPA, and privacy shield. For more details see our Terms and Privacy Policy.</p>
            </details>
          </div>
        </div>
      </div>
    </section>
  </div>
 </Layout>
</template>

<script setup>
import { ref } from 'vue'
import Layout from '../components/Layout.vue'
</script>

<style scoped>
/* Additional styles if needed */
</style>