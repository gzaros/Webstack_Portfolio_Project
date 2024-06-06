<template>
  <a
    :href="href"
    target="_blank"
<<<<<<< HEAD
    class="flex items-center pt-3 px-3 py-2 rounded border-2 text-white border-[#f3aa0f] bg-[#f3aa0f] hover:bg-[#775f2b] hover:border-[#775f2b] transition-colors"
=======
    class="px-3 py-2 rounded border-2 text-white border-[#f3aa0f] bg-[#f3aa0f] hover:bg-[#775f2b] hover:border-[#775f2b] transition-colors"
>>>>>>> d139e79c70908a24bfc4200d71d1f1e8cce6edc7
  >
    <slot
      ><svg
        xmlns="http://www.w3.org/2000/svg"
        width="16"
        height="16"
        fill="currentColor"
<<<<<<< HEAD
        class="bi bi-flag-fill mr-2"
        viewBox="0 0 16 16"
      >
        <path
          d="M14.778.085A.5.5 0 0 1 15 .5V8a.5.5 0 0 1-.314.464L14.5 8l.186.464-.003.001-.006.003-.023.009a12 12 0 0 1-.397.15c-.264.095-.631.223-1.047.35-.816.252-1.879.523-2.71.523-.847 0-1.548-.28-2.158-.525l-.028-.01C7.68 8.71 7.14 8.5 6.5 8.5c-.7 0-1.638.23-2.437.477A20 20 0 0 0 3 9.342V15.5a.5.5 0 0 1-1 0V.5a.5.5 0 0 1 1 0v.282c.226-.079.496-.17.79-.26C4.606.272 5.67 0 6.5 0c.84 0 1.524.277 2.121.519l.043.018C9.286.788 9.828 1 10.5 1c.7 0 1.638-.23 2.437-.477a20 20 0 0 0 1.349-.476l.019-.007.004-.002h.001"
        /></svg
    ></slot>
     {{ href }}
  </a>
=======
        class="bi bi-eye-fill"
        viewBox="0 0 16 16"
      >
        <path d="M10.5 8a2.5 2.5 0 1 1-5 0 2.5 2.5 0 0 1 5 0" />
        <path
          d="M0 8s3-5.5 8-5.5S16 8 16 8s-3 5.5-8 5.5S0 8 0 8m8 3.5a3.5 3.5 0 1 0 0-7 3.5 3.5 0 0 0 0 7"
        /></svg
    ></slot>
  </a>

>>>>>>> d139e79c70908a24bfc4200d71d1f1e8cce6edc7
</template>

<script setup>
const props = defineProps({
  href: String,
});
</script>
