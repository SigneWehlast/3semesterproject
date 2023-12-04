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
    <div v-for="(slide, index) in slides" :key="index" class="customer-logos-slider">
      <div class="slide-content">
        <h3>{{ slide.title }}</h3>
      </div>
      <img :src="slide.image" alt="Slide billede" class="slide-image" />
    </div>
  </div>
</template>

<style scoped>

</style>
