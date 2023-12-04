<script setup>
import { onMounted, ref } from 'vue';

const slides = ref([]);
const error = ref(null);

const getSlides = () => {
  fetch('https://semesterproject-c7cbb-default-rtdb.europe-west1.firebasedatabase.app/vinudstillere.json', {
    method: 'GET'
  })
  .then((res) => res.json())
  .then((res) => {
    console.log('Fetched data:', res);
    if (res && res.slides) {
      slides.value = Object.values(res.slides);
    } else {
      error.value = 'Slides data is undefined or null';
    }
  })
  .catch((err) => {
    console.error(err);
    error.value = 'Could not fetch data';
  });
};

onMounted(() => {
  getSlides();
});
</script>

<template>
  <div class="slideshow-container">
    <div v-for="(slide, index) in slides" :key="index" class="fade">
      <div class="slide-content">
        <h3>{{ slide.title }}</h3>
      </div>
      <img :src="slide.image" alt="Slide billede" class="slide-image" />
    </div>
  </div>
</template>

<style scoped>
.slideshow-container {
  max-width: 1000px;
  margin: auto;
  position: relative;
}

.fade {
  display: none;
  position: absolute;
  width: 100%;
  animation: fade 1.5s ease-in-out infinite;
}

@keyframes fade {
  from {
    opacity: 0.4;
  }
  to {
    opacity: 1;
  }
}

.slide-content {
  position: absolute;
  top: 10px;
  left: 10px;
  z-index: 1;
  color: white;
}
</style>
