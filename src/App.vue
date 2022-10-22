<script setup>
import { ref } from 'vue';
import RatingView from './components/RatingView.vue';
import SubmitView from './components/SubmitView.vue';

const submitRating = ref(false);
const rating = ref(0);
const handleSubmit = (ratingNumber) => {
  submitRating.value = !submitRating.value;
  if(ratingNumber){
    rating.value = ratingNumber;
  }

}
</script>

<template>
  <main>
    <div class="card">
      <RatingView v-show="!submitRating" @handleSubmit="handleSubmit"/>
      <SubmitView v-show="submitRating" @handleBack="handleSubmit" :rating="rating" />
      
    </div>
  </main>
</template>

<style scoped>

</style>
