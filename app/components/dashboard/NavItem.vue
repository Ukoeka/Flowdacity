<template>
  <button
    :class="[
      'w-full flex items-center gap-3 px-3 py-2 rounded-lg text-sm font-medium transition-colors',
      active
        ? 'bg-gray-100 text-gray-900'
        : 'text-gray-600 hover:bg-gray-50 hover:text-gray-900'
    ]"
  >
    <span class="text-lg">{{ icon }}</span>
    <span>{{ label }}</span>
  </button>
</template>

<script setup>
defineProps({
  icon: String,
  label: String,
  active: Boolean,
})
</script>

<style scoped>
button {
  transition-duration: 150ms;
}
</style>