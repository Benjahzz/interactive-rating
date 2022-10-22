<script setup>
import { ref } from 'vue';
const emit = defineEmits(['handleSubmit']);
const rating = ref(0);
const handleRatingButton = (e) => {
    if (document.querySelector('.rating__star.active')) {
        document.querySelector('.rating__star.active').classList.remove('active');
    }
    e.target.classList.add('active');
    rating.value = e.target.dataset.rating;
}
const handleSubmit = (e) => {
    emit('handleSubmit', parseInt(rating.value));
}
</script>

<template>
    <div class="container-rating">
        <div class="logo-star">
            <img src="/images/icon-star.svg" alt="">
        </div>
        <h4>How did we do?</h4>
        <p class="card-text">Please let us know how we did with your support request. All feedback is appreciated
            to help us improve our offering!</p>

        <div class="rating">
            <div class="rating__star" @click="handleRatingButton" data-rating="1">
                1
            </div>
            <div class="rating__star" @click="handleRatingButton" data-rating="2">
                2
            </div>
            <div class="rating__star" @click="handleRatingButton" data-rating="3">
                3
            </div>
            <div class="rating__star" @click="handleRatingButton" data-rating="4">
                4
            </div>
            <div class="rating__star" @click="handleRatingButton" data-rating="5">
                5
            </div>
        </div>
        <button class="btn btn-submit" @click="handleSubmit">SUBMIT</button>

    </div>
</template>
