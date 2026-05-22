<template>
  <div class="min-h-screen flex flex-col">
    <Navbar />
    <div class="pt-16 md:pt-20 flex-1">
      <slot />
    </div>
    <Footer />
  </div>
</template>

<script setup>
import Navbar from './Navbar.vue'
import Footer from './Footer.vue'
</script>

<style scoped>
</style>
