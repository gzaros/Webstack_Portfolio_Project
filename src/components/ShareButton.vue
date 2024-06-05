<template>
  <a
    :href="href"
    target="_blank"
    class="ml-2 px-3 py-2 rounded border-2 text-white border-[#3083b0] bg-[#3083b0] hover:bg-[#22475c] hover:border-[#22475c] transition-colors"
  >
    <slot
      ><svg
        xmlns="http://www.w3.org/2000/svg"
        width="16"
        height="16"
        fill="currentColor"
        class="bi bi-share-fill"
        viewBox="0 0 16 16"
      >
        <path
          d="M11 2.5a2.5 2.5 0 1 1 .603 1.628l-6.718 3.12a2.5 2.5 0 0 1 0 1.504l6.718 3.12a2.5 2.5 0 1 1-.488.876l-6.718-3.12a2.5 2.5 0 1 1 0-3.256l6.718-3.12A2.5 2.5 0 0 1 11 2.5"
        /></svg
    ></slot>
  </a>
</template>

<script setup>
const props = defineProps({
  href: String,
});
</script>
