<template>
  <div class="min-h-screen flex flex-col">
    <Navbar />
    <div class="flex-1">
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
