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

<style scoped>
    .omOs_container {
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .om_box {
        width: 235px;
    }
    .omOs_image {
        height: 100%;
        width: 235px;
        margin-top: 40px;
    }

    .omOs_description {
        margin: 5px -20px 0 -20px;
    }

    /*tablet*/
    @media screen and (min-width: 601px) {
        .omOs_image {
        height: 100%;
        width: 350px;
        margin-top: 40px;
    }
        .om_box {
        width: 350px;
    }
    }

    
    @media only screen and (min-width: 960px) {
    .omOs_container {
        display: flex;
        flex-flow: row wrap;
        justify-content: space-evenly;
        margin: 20px;
        align-items: self-start;
    }

    .omOs_description {
        margin: 0px -20px 0px -20px;
    }

    }

</style>
