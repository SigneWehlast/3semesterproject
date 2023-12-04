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
    <div class="container_distance">
    <div class="container">
      <div v-for="(laerMereSection, index) in laerMere" :key="index" class="laerMere_box">
        <div class="content_container">
          <h3 class="laerMere_h3">{{ laerMereSection.title }}</h3>
          <p class="laerMere_p">{{ laerMereSection.description }}</p>
            <div @click="aboutUsScroll()" class="btn pink laesmere_btn">LÆS MERE</div>
        </div>
        <div class="image_container">
          <img :src="laerMereSection.image" alt="Lær mere billede" class="laerMere_image" />
        </div>
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

.laerMere_box {
  display: flex;
  border: 1px solid;
  margin: 10px;
  width: 80%;
  height: auto;  
  background-color: #FFFFFF;
  border-color: #707070;
}

.laerMere_p {
  font-size: 14px;
  color: #2D3142;
  padding-right: 20px;
  padding-left: 20px;
  line-height: 15px;
}

.content_container {
  flex: 1;
  text-align: left;
}

.image_container {
    width: 30%;
}

.laerMere_image {
    height: 100%;
    width: 100%;
    object-fit: cover;
}

.laesmere_btn {
    margin: 10px 0px 10px 20px;
}

.laerMere_h3 {
    margin-left: 20px;
}

/*tablet */
@media screen and (min-width: 601px) {
.laesmere_btn {
    margin-top: 35px;
}
.laerMere_h3 {
    margin-top: 20px;
}
}

/*web */
@media only screen and (min-width: 960px) {
.container_distance {
    display: flex;
    justify-content: center;
  }
  
   .laerMere_box {
      display: flex;
      flex-direction: column-reverse;
      height: 400px;
    }
  
    .container {
      flex-direction: row;
      width: 90%;
    }
  
    .content_container {
      display: flex;
      align-items: center;
      justify-content: space-evenly;
      flex-direction: column;
    }
    .laerMere_container{
      width: 100%;
    }

    .image_container {
        width: 100%;
        height: 40%;
    }

    .laesmere_btn {
        margin: 10px 0px 10px 0px;
    }

    .laerMere_h3
    {
        margin: 0;
        
    }
}

</style>