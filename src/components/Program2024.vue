<script setup>
import{
  onMounted,
  ref
} from 'vue';
/*const props = defineProps ([ 'programData' ]);*/
const props = ([ 'time','image','description' ])

const fProgram = ref({});
const error = ref(null);

onMounted(() => {
  getForsideProgram();
  console.log("pøls");
});

const getForsideProgram = () => {
  fetch('https://semesterproject-c7cbb-default-rtdb.europe-west1.firebasedatabase.app/forsideprogram.json', {
    method: 'GET'
  })
  .finally(console.log("tis"))
  .then((res) => res.json())
  .then((res) => {
    console.log(res);
    fProgram.value = res;
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
    </div>-->
    <div class="program_box">
        <h3>{{ time }}</h3>
        <p> {{ description }}</p>
        <img :src="image" alt="program billede" />
    </div>
</template>