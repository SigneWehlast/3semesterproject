<script setup>
import{
  onMounted,
  ref
} from 'vue';
/*const props = defineProps ([ 'programData' ]);*/
/*const props = defineProps([ 'time', 'description', 'image' ])*/

const fProgram = ref([]);
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
    console.log(fProgram)
  })
  .catch((err) => {
  console.log(err);
  error.value = 'Kunne ikke hente data';
  });
};

</script>

<template>
  <!--  <div class="program_box">
        <p>{{ programData.time }}</p>
        <p> {{ programData.description }}</p>
        <img :src="programData.image" alt="program billede" />
    </div>
    <div class="program_box">
        <h3>{{ props.time }}</h3>
        <p> {{ props.description }}</p>
        <img :src="props.image" alt="program billede" />
        {{  fProgram }}
    </div> -->
    <div class="program_box">
        <h3>{{ fProgram.time }}</h3>
        <p>{{ fProgram.description }}</p>
        <img :src="fProgram.image" alt="Program billede" />
    </div>
</template>