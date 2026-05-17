<template>
  <nav class="fixed top-0 left-0 w-full z-50 flex items-center justify-between px-8 py-4 bg-white border-b border-gray-200 shadow">
    <div class="flex items-center gap-2">
      <div class="w-8 h-8 bg-purple-500 rounded-full flex items-center justify-center">
        <span class="text-white font-bold text-lg">F</span>
      </div>
      <span class="text-xl font-bold text-gray-900">Flowdacity</span>
    </div>

    <div class="hidden md:flex items-center gap-8">
      <a href="/products" class="text-gray-700 hover:text-gray-900">Products</a>
      <a href="/customers" class="text-gray-700 hover:text-gray-900">Customers</a>
      <a href="/developers" class="text-gray-700 hover:text-gray-900">Developers</a>
      <a href="/resources" class="text-gray-700 hover:text-gray-900">Resources</a>
      <a href="/pricing" class="text-gray-700 hover:text-gray-900">Pricing</a>
    </div>

    <div class="flex items-center gap-4">
      <NuxtLink to="/auth/login" class="text-gray-700 hover:text-gray-900 font-medium">LOG IN</NuxtLink>
      <NuxtLink to="/auth/signup" class="px-6 py-2 border-2 border-gray-900 text-gray-900 rounded hover:bg-gray-900 hover:text-white transition">SIGN UP</NuxtLink>
    </div>
  </nav>
</template>

<script setup>

</script>

<style scoped>
</style>
