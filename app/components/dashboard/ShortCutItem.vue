<template>
  <div class="text-center">
    <p class="text-2xl font-bold text-gray-900">{{ value }}</p>
    <p class="text-xs text-gray-500 mt-1">{{ label }}</p>
  </div>
</template>

<script setup>
defineProps({
  label: String,
  value: String,
})
</script>

<style scoped>
</style>