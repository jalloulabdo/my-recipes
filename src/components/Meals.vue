<template>
  <div class="hero-full-wrapper">
    <div class="grid">
      <div class="gutter-sizer"></div>
      <div class="grid-sizer"></div>
      <MealItem v-for="meal of meals" :key="meal.idMeal" :meal="meal" />
    </div>
  </div>
  <div v-if="!meals.length" class="flex justify-center text-gray-600 p-8">
    There are no meals
  </div>
  <div id="scripts"></div>

</template>


<script setup>
import MealItem from './MealItem.vue';
import { computed, onMounted, ref } from "vue";

const { meals } = defineProps({
  meals: {
    required: true,
    type: Array,
  }
})
onMounted(async () => {
  var src = [
    '/assets/main.85741bff.js',
  ]
  for (let i = 0; i < src.length; i++) {
    const script = document.createElement('script');
    script.src = src[i];
    script.async = false;
    document.getElementById('scripts').appendChild(script)
  }

  masonryBuild();
});
</script>
