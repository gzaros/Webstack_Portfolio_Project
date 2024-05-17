<template>
  <a
    :href="href"
    target="_blank"
    class="px-3 py-2 rounded border-2 text-white border-gray-600 bg-gray-500 hover:bg-gray-600 transition-colors"
  >
    <slot>Details</slot>
  </a>
</template>

<script setup>
const props = defineProps({
  href: String
})
</script>
