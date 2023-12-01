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
  <div class="historie_container">
    <div v-for="(historieSection, index) in historie" :key="index" class="historie_box">
        <div class="">
            <p class="historie_description">{{ historieSection.description }}</p>
        </div>  
        <div class="">
            <img :src="historieSection.image" alt="historie billede" class="historie_image" />
        </div>
        <div class="">
            <p class="historie_title">{{ historieSection.title }}</p>
        </div> 
    </div>
  </div>
</template>

<style scoped>
    .historie_container {
        display: flex;
        flex-direction: column;
    }
    .historie_box {
        width: 235px;
        margin-left: 20px;
    }
    .historie_image {
        height: 100%;
        width: 235px;
    }

    .historie_description {
        margin: 40px -20px 0 -20px;
    }

    .historie_title {
        text-align: center;
        /*margin-left: -20px;*/
    }

    @media screen and (min-width: 601px) {
        .historie_image {
        height: 100%;
        width: 350px;
    }
        .historie_box {
        width: 350px;
    }
    }
</style>