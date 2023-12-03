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
  <div class="container_distance">
    <div class="container">
      <div v-for="(program, index) in fProgram" :key="index" class="program_box">
        <div class="content_container">
          <h3>{{ program.time }}</h3>
          <p class="content_p">{{ program.description }}</p>
        </div>
        <div class="image_container">
          <img :src="program.image" alt="Program billede" class="program_image" />
        </div>
      </div>
    </div>
  </div>
</template>