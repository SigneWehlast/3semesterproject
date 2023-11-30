<script setup>
import{
  onMounted,
  ref
} from 'vue';
/*const props = defineProps ([ 'programData' ]);*/
/*const props = defineProps([ 'time', 'description', 'image' ])*/

const fProgram = ref({});
const error = ref(null);

onMounted(() => {
  getForsideProgram();
});

const getForsideProgram = () => {
  fetch('https://semesterproject-c7cbb-default-rtdb.europe-west1.firebasedatabase.app/forsideprogram.json', {
    method: 'GET'
  })
  .then((res) => res.json())
  .then((res) => {
    console.log(res);
    fProgram.value = res;
    console.log(fProgram.value)
  })
  .catch((err) => {
  console.log(err);
  error.value = 'Kunne ikke hente data';
  });
};

</script>
<template>
  <div class="container">
    <div v-for="(program, index) in fProgram" :key="index" class="program_box">
      <div class="content_container">
        <h3>{{ program.time }}</h3>
        <p>{{ program.description }}</p>
      </div>
      <div class="image_container">
        <img :src="program.image" alt="Program billede" class="program_image" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column; /* Gør containeren til en lodret flex-container */
  align-items: center;
  height: 100vh; /* Gør containeren 100% af viewportens højde */
}

.program_box {
  display: flex;
  border: 1px solid #ccc;
  padding: 10px;
  margin: 10px;
}

.content_container {
  flex: 1;
  text-align: left;
}

.image_container {
  width: 100px; /* Juster denne værdi efter dine behov */
  height: 100px; /* Juster denne værdi efter dine behov */
  overflow: hidden;
  margin-left: 10px;
}

.program_image {
  width: 100%;
  height: auto;
}
</style>