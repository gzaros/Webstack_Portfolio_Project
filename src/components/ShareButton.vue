<template>
  <a
    href="javascript:void(0);"
    @click="shareOnFacebook"
    target="_blank"
    class="flex items-center  ml-2 px-3 py-2 rounded border-2 text-white border-[#3083b0] bg-[#3083b0] hover:bg-[#22475c] hover:border-[#22475c] transition-colors"
  >
    <svg
      xmlns="http://www.w3.org/2000/svg"
      width="16"
      height="16"
      fill="currentColor"
      class="bi bi-tags mr-2"
      viewBox="0 0 16 16"
    >
      <path
        d="M3 2v4.586l7 7L14.586 9l-7-7zM2 2a1 1 0 0 1 1-1h4.586a1 1 0 0 1 .707.293l7 7a1 1 0 0 1 0 1.414l-4.586 4.586a1 1 0 0 1-1.414 0l-7-7A1 1 0 0 1 2 6.586z"
      />
      <path
        d="M5.5 5a.5.5 0 1 1 0-1 .5.5 0 0 1 0 1m0 1a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3M1 7.086a1 1 0 0 0 .293.707L8.75 15.25l-.043.043a1 1 0 0 1-1.414 0l-7-7A1 1 0 0 1 0 7.586V3a1 1 0 0 1 1-1z"
      /></svg
    >{{ href }}
  </a>
</template>

<script setup>
const props = defineProps({
  href: String,
});

// Function to handle the Facebook share
function shareOnFacebook() {
  const url = "http://localhost:3000/meal/" + encodeURIComponent(props.href);
  console.debug(url);
  const shareUrl = `https://www.facebook.com/sharer/sharer.php?u=${url}`;
  window.open(shareUrl, "_blank", "width=600,height=400");
}
</script>
