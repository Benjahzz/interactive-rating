<script setup>
    const emit = defineEmits(['handleBack']);
    const props = defineProps({
        rating: {
            type: Number,
            required: true
        }
    });
    const handleBack = () => {
        emit('handleBack');
    }
</script>
<template>
    <div class="confirmation">
        <div class="confirmation__logo-check">
            <img src="/images/illustration-thank-you.svg" alt="">
        </div>
        <p class="confirmation__rating__text">You selected {{rating}} out of 5</p>
        <h1 class="confirmation__title">Thank you!</h1>
        <p class="confirmation__text">We appreciate you taking the time to give a rating. If you ever need more support,
            don't hesitate to get in touch!
        </p>
        <button class="btn" @click="handleBack">BACK TO HOME</button>
    </div>
</template>
