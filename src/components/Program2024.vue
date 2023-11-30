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
        <p class="content_p">{{ program.description }}</p>
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
  flex-direction: column; 
  align-items: center;
  padding-bottom: 20px; 
}

.program_box {
  display: flex;
  border: 1px solid #ccc;
  padding: 20px;
  margin: 10px;
  width: 80%;
}

.content_p {
  font-size: 14px;
  color: #2D3142;
  padding-right: 20px;
  padding-left: 0px;
  line-height: 15px;
}

.content_container {
  flex: 1;
  text-align: left;
}

.image_container {
  width: 100px; 
  height: 100px; 
  overflow: hidden;
  margin-left: 10px;
}

.program_image {
  width: 100%;
  height: auto;
}
</style>