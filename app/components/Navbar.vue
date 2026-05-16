<template>
  <nav class="flex items-center justify-between px-8 py-6 bg-white border-b border-gray-200">
    <div class="flex items-center gap-2">
      <div class="w-8 h-8 bg-green-500 rounded-full flex items-center justify-center">
        <span class="text-white font-bold text-lg">F</span>
      </div>
      <span class="text-xl font-bold text-gray-900">Flowdacity</span>
    </div>

    <div class="hidden md:flex items-center gap-8">
      <a href="#" class="text-gray-700 hover:text-gray-900">Products</a>
      <a href="#" class="text-gray-700 hover:text-gray-900">Customers</a>
      <a href="#" class="text-gray-700 hover:text-gray-900">Developers</a>
      <a href="#" class="text-gray-700 hover:text-gray-900">Resources</a>
      <a href="#" class="text-gray-700 hover:text-gray-900">Pricing</a>
    </div>

    <div class="flex items-center gap-4">
      <NuxtLink to="/auth/login" class="text-gray-700 hover:text-gray-900 font-medium">LOG IN</NuxtLink>
      <NuxtLink to="/auth/signup" class="px-6 py-2 border-2 border-gray-900 text-gray-900 rounded hover:bg-gray-900 hover:text-white transition">SIGN UP</NuxtLink>
    </div>
  </nav>
</template>
