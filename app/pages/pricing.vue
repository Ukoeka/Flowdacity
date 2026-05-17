<template>
  <Layout>
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
  </Layout>
</template>

<script setup>
import Layout from '../components/Layout.vue'
</script>

<style scoped>
</style>
