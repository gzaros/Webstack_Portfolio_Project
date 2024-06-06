<template>
  <header class="bg-[#04466c] shadow h-16 flex justify-between items-center px-4">
    <router-link
      :to="{ name: 'home' }"
      class="inline-flex items-center h-full text-white font-bold"
    >
      Management the World's Meals
    </router-link>
    <button @click="toggleMenu" class="text-white md:hidden focus:outline-none">
      <svg
        class="w-6 h-6"
        fill="none"
        stroke="currentColor"
        viewBox="0 0 24 24"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M4 6h16M4 12h16m-7 6h7"
        ></path>
      </svg>
    </button>
    <nav
      :class="{ hidden: !isMenuOpen }"
      class="hidden md:flex items-center gap-1"
    >
      <router-link
        :to="{ name: 'byName' }"
        class="justify-between items-center inline-flex px-2 py-1 transition-colors text-gray-400 hover:bg-gray-700 hover:text-white"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="16"
          height="16"
          fill="currentColor"
          class="bi bi-search mr-1"
          viewBox="0 0 16 16"
        >
          <path
            d="M11.742 10.344a6.5 6.5 0 1 0-1.397 1.398h-.001q.044.06.098.115l3.85 3.85a1 1 0 0 0 1.415-1.414l-3.85-3.85a1 1 0 0 0-.115-.1zM12 6.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0"
          /></svg
        >Search Meals
      </router-link>
      <router-link
        :to="{ name: 'byLetter' }"
        class="justify-between items-center inline-flex px-2 py-1 transition-colors text-gray-400 hover:bg-gray-700 hover:text-white"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="16"
          height="16"
          fill="currentColor"
          class="bi bi-filter-square-fill mr-1"
          viewBox="0 0 16 16"
        >
          <path
            d="M2 0a2 2 0 0 0-2 2v12a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V2a2 2 0 0 0-2-2zm.5 5h11a.5.5 0 0 1 0 1h-11a.5.5 0 0 1 0-1M4 8.5a.5.5 0 0 1 .5-.5h7a.5.5 0 0 1 0 1h-7a.5.5 0 0 1-.5-.5m2 3a.5.5 0 0 1 .5-.5h3a.5.5 0 0 1 0 1h-3a.5.5 0 0 1-.5-.5"
          /></svg
        >Meals By Letter
      </router-link>
      <router-link
        :to="{ name: 'ingredients' }"
        class="justify-between items-center inline-flex px-2 py-1 transition-colors text-gray-400 hover:bg-gray-700 hover:text-white"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="16"
          height="16"
          fill="currentColor"
          class="bi bi-funnel-fill mr-1"
          viewBox="0 0 16 16"
        >
          <path
            d="M1.5 1.5A.5.5 0 0 1 2 1h12a.5.5 0 0 1 .5.5v2a.5.5 0 0 1-.128.334L10 8.692V13.5a.5.5 0 0 1-.342.474l-3 1A.5.5 0 0 1 6 14.5V8.692L1.628 3.834A.5.5 0 0 1 1.5 3.5z"
          /></svg
        >Meals By Ingredients
      </router-link>
    </nav>
  </header>
  <div v-if="isMenuOpen" class="md:hidden bg-black">
    <router-link
      :to="{ name: 'byName' }"
      class="block px-4 py-2 transition-colors text-gray-400 hover:bg-gray-700 hover:text-white"
      @click="toggleMenu"
    >
      Search Meals
    </router-link>
    <router-link
      :to="{ name: 'byLetter' }"
      class="block px-4 py-2 transition-colors text-gray-400 hover:bg-gray-700 hover:text-white"
      @click="toggleMenu"
    >
      Meals By Letter
    </router-link>
    <router-link
      :to="{ name: 'ingredients' }"
      class="block px-4 py-2 transition-colors text-gray-400 hover:bg-gray-700 hover:text-white"
      @click="toggleMenu"
    >
      Meals By Ingredients
    </router-link>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isMenuOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
  },
};
</script>

<style scoped>
/* Additional custom styles if needed */
</style>
