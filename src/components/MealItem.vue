<template>
  <div class="grid-item">
    <router-link :to="{ name: 'mealDetails', params: { id: meal.idMeal } }">
      <img class="img-responsive" :src="meal.strMealThumb" :alt="meal.strMeal">
    </router-link>
    <router-link class="project-description" :to="{ name: 'mealDetails', params: { id: meal.idMeal } }">

      <div class="project-text-holder">
        <div class="project-text-inner">
          <h3 style="font-size: 23px;">{{ meal.strMeal }}</h3>
          <p>Discover more</p>
          <!-- <div class="flex items-center justify-center">
            <YouTubeButton :href="meal.strYoutube" />
          </div> -->
        </div>
      </div>
    </router-link>
  </div>

</template>



<script setup>
import YouTubeButton from './YouTubeButton.vue';
import { computed, onMounted, ref } from "vue";

const { meal } = defineProps({
  meal: {
    required: true,
    type: Object
  }
})
onMounted(async () => {
  masonryBuild();
});
</script>
