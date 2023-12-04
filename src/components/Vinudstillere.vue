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
        <div v-for="(slide, index) in slides" :key="index" class="slide">
            <img :src="slide.image" alt="Slide billede" class="slide-image" />
        </div>
    </div>
  </div>
</template>

<style scoped>
@keyframes scroll {
	 0% {
		 transform: translateX(0);
	}
	 100% {
        transform: translateX(calc(-250px * 7));
	}
}
 .slideshow-container {
	 height: 200px;
	 margin-top: 50px;
	 margin-bottom: 50px;
	 overflow: hidden;
	 position: relative;
	 justify-content: center;
	 align-items: center;
     width: auto;
}
 .slideshow-container .slider-track {
	 animation: scroll 10s linear infinite;
	 display: flex;

}
 .slideshow-container .slider-track .slide {
	 height: 200px;
	 margin-left: 30px;
	 margin-right: 30px;
     padding-bottom: 30px;
     padding-right: 30px;
     padding-left: 30px;
     background-color: white;
	 position: relative;
}
 .slideshow-container .slider-track .slide img {
	 filter: grayscale(100%);
	 transition: filter 0.3s ease;
	 height: 100%;
	 width: 100%;
	 object-fit: cover;
}
 .slideshow-container .slider-track .slide:hover {
	 filter: grayscale(0%);
}
 .slideshow-container .slider-track .slide + .logo-overlay {
	 opacity: 0;
	 transition: opacity 0.3s ease;
}
 .slideshow-container .slider-track .slide:hover + .logo-overlay {
	 opacity: 1;
}
 .slideshow-container:hover .slide {
	 animation-play-state: paused;
}
 .slideshow-container .logo-overlay {
	 position: absolute;
	 top: 0;
	 left: 0;
	 width: 100%;
	 height: 100%;
	 opacity: 0;
	 transition: opacity 0.3s ease;
}
 .slider:hover .logo-overlay {
	 opacity: 1;
}
 
</style>
