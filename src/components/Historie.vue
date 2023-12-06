<script setup>

import{
  onMounted,
  ref
} from 'vue';

const historie = ref({});
const error = ref(null);

onMounted(() => {
  getHistorieSection();
});

const getHistorieSection = () => {
  fetch('https://semesterproject-c7cbb-default-rtdb.europe-west1.firebasedatabase.app/historie.json', {
    method: 'GET'
  })
  .then((res) => res.json())
  .then((res) => {
    console.log(res);
    historie.value = res;
    console.log(historie.value)
  })
  .catch((err) => {
  console.log(err);
  error.value = 'Kunne ikke hente data';
  });
};

</script>
<template>
  <section id="historie_section">
    <div class="historie_container">
      <div v-for="(historieSection, index) in historie" :key="index" class="historie_box">
          <div class="">
              <p class="historie_description">{{ historieSection.description }}</p>
          </div>  
          <div class="">
              <img id="historie_img" :src="historieSection.image" alt="historie billede" class="historie_image" />
          </div>
          <div class="">
              <p class="historie_title">{{ historieSection.title }}</p>
          </div> 
      </div>
    </div>
  </section>
</template>
