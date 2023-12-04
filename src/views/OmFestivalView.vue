<script setup>
import RiedelGlas from '../components/RiedelGlas.vue';
import LaerMere from '../components/LaerMere.vue';
import OmOS from '../components/OmOs.vue';
import Historie from '../components/Historie.vue';

const aboutScroll = () => {
  document.getElementById("udforsk_scroll").scrollIntoView({ behavior: "smooth" });
    };

</script>

<template>
  <main>
    <h2>OM ROSÉ FESTIVAL ODENSE</h2>
    <div class="center">
          <video class="hero_movie" controls>
            <source src="../assets/videos/rosefestivalodense_headvideo.mp4" type="video/mp4">
          </video>
        </div>
        <div class="btn pink udforsk_btn" @click="aboutScroll()">UDFORSK</div>
  </main>
  <section class="pinkbackground">
    <h2 id="udforsk_scroll">LÆR MERE OM FESTIVALEN</h2>
    <LaerMere />
  </section>
  <section>
    <h2>OM OS</h2>
    <OmOS />
  </section>
  <section class="pinkbackground">
    <h2>HISTORIEN OM ROSÉ FESTIVAL ODENSE</h2>
    <Historie />
  </section>
  <section>
    <h2>RIEDEL GLAS</h2>
    <RiedelGlas />
  </section>
</template>
