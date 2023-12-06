<script setup>

import{
  onMounted,
  ref
} from 'vue';

const omOs = ref({});
const error = ref(null);

onMounted(() => {
  getOmOsSection();
});

const getOmOsSection = () => {
  fetch('https://semesterproject-c7cbb-default-rtdb.europe-west1.firebasedatabase.app/omos.json', {
    method: 'GET'
  })
  .then((res) => res.json())
  .then((res) => {
    console.log(res);
    omOs.value = res;
    console.log(omOs.value)
  })
  .catch((err) => {
  console.log(err);
  error.value = 'Kunne ikke hente data';
  });
};

</script>
<template>
  <div class="omOs_container">
    <div v-for="(omSection, index) in omOs" :key="index" class="om_box">
        <div class="">
            <img :src="omSection.image" alt="Om os billede" class="omOs_image" />
        </div>
        <div class="">
            <p class="omOs_description">{{ omSection.description }}</p>
        </div>  
    </div>
  </div>
</template>
