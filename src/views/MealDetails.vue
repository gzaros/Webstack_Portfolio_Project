<template>
  <div class="max-w-[99%] mx-auto p-8">
    <h1 class="text-4xl font-bold mb-5 text-[#04466c]">{{ meal.strMeal }}</h1>
    <div class="flex flex-wrap items-start">
      <div class="w-full sm:w-1/2 pr-4 mb-4">
        <img :src="meal.strMealThumb" :alt="meal.strMeal" class="w-full" />

        <div class="mt-3 grid grid-cols-1 sm:grid-cols-2">
          <div>
            <h2
              class="ml-2 px-3 py-2 rounded border-2 text-white border-[#a1a3a4] bg-[#a1a3a4] hover:bg-[#22475c] hover:border-[#22475c] transition-colors flex items-center text-2xl font-semibold mb-2"
            >
              Ingredients
            </h2>
            <ul>
              <template v-for="(el, ind) of new Array(20)">
                <li v-if="meal[`strIngredient${ind + 1}`]">
                  {{ ind + 1 }}. {{ meal[`strIngredient${ind + 1}`] }}
                </li>
              </template>
            </ul>
          </div>
          <div>
            <h2
              class="ml-2 px-3 py-2 rounded border-2 text-white border-[#a1a3a4] bg-[#a1a3a4] hover:bg-[#22475c] hover:border-[#22475c] transition-colors flex items-center text-2xl font-semibold mb-2"
            >
              Measures
            </h2>
            <ul>
              <template v-for="(el, ind) of new Array(20)">
                <li v-if="meal[`strMeasure${ind + 1}`]">
                  {{ ind + 1 }}. {{ meal[`strMeasure${ind + 1}`] }}
                </li>
              </template>
            </ul>
          </div>
        </div>
      </div>
      <div class="w-full sm:w-1/2 mb-4">
        <div class="pb-5 border-gray-300 grid grid-cols-1 sm:grid-cols-3">
          <button
            @click="toggleVideoSection"
            id="btnaction"
            href="javascript:void(0);"
            target="_blank"
            v-if="showVideo"
            class="ml-2 px-3 py-2 rounded border-2 text-white border-[#3083b0] bg-[#3083b0] hover:bg-[#22475c] hover:border-[#22475c] transition-colors flex items-center"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="16"
              height="16"
              fill="currentColor"
              class="bi bi-chat-square-text-fill mr-2"
              viewBox="0 0 16 16"
            >
              <path
                d="M0 2a2 2 0 0 1 2-2h12a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2h-2.5a1 1 0 0 0-.8.4l-1.9 2.533a1 1 0 0 1-1.6 0L5.3 12.4a1 1 0 0 0-.8-.4H2a2 2 0 0 1-2-2zm3.5 1a.5.5 0 0 0 0 1h9a.5.5 0 0 0 0-1zm0 2.5a.5.5 0 0 0 0 1h9a.5.5 0 0 0 0-1zm0 2.5a.5.5 0 0 0 0 1h5a.5.5 0 0 0 0-1z"
              /></svg
            >Description
          </button>
          <button
            @click="toggleVideoSection"
            id="btnaction"
            href="javascript:void(0);"
            target="_blank"
            v-if="!showVideo"
            class="ml-2 px-3 py-2 rounded border-2 text-white border-[#3083b0] bg-[#3083b0] hover:bg-[#22475c] hover:border-[#22475c] transition-colors flex items-center"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="16"
              height="16"
              fill="currentColor"
              class="bi bi-youtube mr-2"
              viewBox="0 0 16 16"
            >
              <path
                d="M8.051 1.999h.089c.822.003 4.987.033 6.11.335a2.01 2.01 0 0 1 1.415 1.42c.101.38.172.883.22 1.402l.01.104.022.26.008.104c.065.914.073 1.77.074 1.957v.075c-.001.194-.01 1.108-.082 2.06l-.008.105-.009.104c-.05.572-.124 1.14-.235 1.558a2.01 2.01 0 0 1-1.415 1.42c-1.16.312-5.569.334-6.18.335h-.142c-.309 0-1.587-.006-2.927-.052l-.17-.006-.087-.004-.171-.007-.171-.007c-1.11-.049-2.167-.128-2.654-.26a2.01 2.01 0 0 1-1.415-1.419c-.111-.417-.185-.986-.235-1.558L.09 9.82l-.008-.104A31 31 0 0 1 0 7.68v-.123c.002-.215.01-.958.064-1.778l.007-.103.003-.052.008-.104.022-.26.01-.104c.048-.519.119-1.023.22-1.402a2.01 2.01 0 0 1 1.415-1.42c.487-.13 1.544-.21 2.654-.26l.17-.007.172-.006.086-.003.171-.007A100 100 0 0 1 7.858 2zM6.4 5.209v4.818l4.157-2.408z"
              ></path>
            </svg>
            Video
          </button>
        </div>
        <div id="sectiondescription">
          <div
            class="pb-5 border-b border-gray-300 grid grid-cols-1 sm:grid-cols-3"
          >
            <div>
              <strong class="font-bold">Category:</strong>
              {{ meal.strCategory }}
            </div>
            <div>
              <strong class="font-bold">Area:</strong> {{ meal.strArea }}
            </div>
            <div>
              <strong class="font-bold">Tags:</strong> {{ meal.strTags }}
            </div>
          </div>
          <p v-if="!showVideo" class="pt-2 text-lg mb-3">
            {{ meal.strInstructions }}
          </p>
        </div>
        <div v-if="showVideo" id="sectionvideo">
          <iframe
            width="420"
            height="405"
            :src="`https://www.youtube-nocookie.com/embed/${meal.strYoutube.replace('https://www.youtube.com/watch?v=', '')}`"
            title="YouTube video player"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            class="min-w-[100%] min-h-[100%] mb-4 mt-2"
            allowfullscreen=""
          ></iframe>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
<<<<<<< HEAD
import { onMounted, ref } from "vue";
import { useRoute } from "vue-router";
import axiosClient from "../axiosClient";
import DetailButton from "../components/DetailButton.vue";
=======
import { onMounted, ref } from 'vue'
import { useRoute } from 'vue-router';
import axiosClient from '../axiosClient';
import DetailButton from '../components/DetailButton.vue';
>>>>>>> d139e79c70908a24bfc4200d71d1f1e8cce6edc7

const route = useRoute();
const meal = ref({});

const showVideo = ref(false);


const toggleVideoSection = () => {
  showVideo.value = !showVideo.value;
};

onMounted(() => {
  axiosClient.get(`lookup.php?i=${route.params.id}`).then(({ data }) => {
    meal.value = data.meals[0] || {};
  });
});
</script>