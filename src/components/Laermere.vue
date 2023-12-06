<script setup>
import{
  onMounted,
  ref
} from 'vue';

const laerMere = ref({});
const error = ref(null);

onMounted(() => {
  getLaerMere();
});

const getLaerMere = () => {
  fetch('https://semesterproject-c7cbb-default-rtdb.europe-west1.firebasedatabase.app/laermere.json', {
    method: 'GET'
  })
  .then((res) => res.json())
  .then((res) => {
    console.log(res);
    laerMere.value = res;
    console.log(laerMere.value)
  })
  .catch((err) => {
  console.log(err);
  error.value = 'Kunne ikke hente data';
  });
};

const aboutUsScroll = () => {
  document.getElementById("aboutUs_scroll").scrollIntoView({ behavior: "smooth" });
    };
</script>

<template>
    <div class="container_distance_lm">
    <div class="container_laermere">
      <div v-for="(laerMereSection, index) in laerMere" :key="index" class="laerMere_box">
        <div class="content_container content_container_lm">
          <h3 class="laerMere_h3">{{ laerMereSection.title }}</h3>
          <p class="laerMere_p">{{ laerMereSection.description }}</p>
            <div @click="aboutUsScroll()" class="btn pink laesmere_btn">LÆS MERE</div>
        </div>
        <div class="image_container_lm">
          <img :src="laerMereSection.image" alt="Lær mere billede" class="laerMere_image" />
        </div>
      </div>
    </div>
  </div>
</template>