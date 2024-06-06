<template>
  <div
    class="bg-white shadow rounded-xl hover:scale-105 transition-all"
  >
    <router-link :to="{ name: 'mealDetails', params: { id: meal.idMeal } }">
      <img
        :src="meal.strMealThumb"
        :alt="meal.strMeal"
        class="rounded-t-xl w-full h-48 object-cover"
      />
    </router-link>
    <div class="p-3">
      <h3 class="font-bold">{{ meal.strMeal }}</h3>
      <p class="mb-4">
        {{ $filters.truncateWords(meal.strInstructions, 20) }}
      </p>
      <div class="flex ">
<<<<<<< HEAD
        <DetailButton :href="meal.strArea" />
        <ShareButton :href="meal.strCategory" />
=======
<<<<<<< HEAD
        <DetailButton :href="meal.strArea" />
        <ShareButton :href="meal.strCategory" />
=======
        <DetailButton :href="meal.strYoutube" />
        <ShareButton :href="meal.strYoutube" />
>>>>>>> d139e79c70908a24bfc4200d71d1f1e8cce6edc7
>>>>>>> origin/master
      </div>
    </div>
  </div>
</template>

<script setup>
import DetailButton from './DetailButton.vue';
import ShareButton from './ShareButton.vue';

const { meal } = defineProps({
  meal: {
    required: true,
    type: Object
  }
})

</script>
