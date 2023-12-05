<script setup>
import { onMounted, ref } from 'vue';

const slides = ref({});
const error = ref(null);

onMounted(() => {
  getSlides();
});



const getSlides = () => {
  fetch('https://semesterproject-c7cbb-default-rtdb.europe-west1.firebasedatabase.app/vinudstillere.json', {
    method: 'GET'
  })
  .then((res) => res.json())
  .then((res) => {
    console.log(res);
    slides.value = res;
    console.log(slides.value)
  })
  .catch((err) => {
    console.error(err);
    error.value = 'Kunne ikke hente data';
  });
};

</script>

<template>
  <div class="slideshow-container">
        <div class="slider-track">
            <img div v-for="(slide, index) in slides" :key="index" class="slide" :src="slide.image" alt="Slide billede" />
        </div>
        <div class="slider-track">
            <img v-for="(slide2, index) in slides" :key="index" class="slide" :src="slide2.image" alt="Slide billede" />
        </div>
  </div>
</template>

<style scoped>

@keyframes slide {
    from {
        transform: translateX(0);
    }
    to {
        transform: translateX(-100%);
    }
}

.slideshow-container {
    overflow: hidden;
    padding: 60px 0;
    white-space: nowrap;
}

.slideshow-container:hover .slider-track{
    animation-play-state: paused;
}
.slider-track {
    display: inline-block;
    box-sizing: border-box;
    animation: 20s slide infinite linear;
}

.slider-track img {
    height: 200px;
    margin: 0 40px;

}

@media screen and (min-width: 900px){
    .slider-track img {
        height: 300px;
    }
}
    

</style>
