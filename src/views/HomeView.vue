<script setup>
  import { Swiper, SwiperSlide } from 'swiper/vue';

// Import Swiper styles
import 'swiper/css';

import Program2024 from '../components/program2024.vue';
import Vinudstillere from '../components/Vinudstillere.vue';

</script>

<template>
  <main>
    <section>
      <!--hero-->
    </section>
    <section class="welcome_container">
      <div class="welcome_leftalign">
        <h2 class="h2_leftalign">VELKOMMEN TIL ROSÉ FESTIVAL ODENSE</h2>
        <p>Odenses største og pinkeste rosé festival har 
          eksisteret siden 2018 og formår hvert år at levere et 
          brag af en festival fyldt med</p>
        
        <div class="symbol"><!--Symbol-->
          <img src="../assets/pictures/champagne-glass.png" alt="icon af glas der skåler" />
          <p>Underholdning</p>
        </div>
        <div class="symbol"><!--Symbol-->
          <img src="../assets/pictures/speech-bubbles-comment-option.png" alt="icon af talebobler" />
          <p>Socialisering & god stemning</p>
        </div>
        <div class="symbol"><!--Symbol-->
          <img src="../assets/pictures/fork-and-knife.png" alt="icon af kniv og gafler" />
          <p>Lækker mad & Iskold Rosé</p>
        </div>
        <div class="symbol"><!--Symbol-->
          <img src="../assets/pictures/music-player.png" alt="icon af en node" />
          <p>Efterfest med DJ</p>
        </div>

        <p>Billetten til festivalen koster 499 kr., hvilket 
          inkluderer 15 slags rosévine fra forskellige 
          forhandlere, en stemningsfuld festivalplads. 
          Derudover får du dit helt eget indgraverede Riedel 
          “Vinum Extreme Rose”-glas, så dine smagninger har 
          de bedste forudsætninger.
        </p>
      </div>
      <div class="welcome_rightalign">
        <div class="center">
        <img src="../assets/pictures/billet.png" class="billet" alt="Ilustration af et par billeter til Rosé Festival Odense" />
        </div>
        <div class="btn blue">KØB BILLET</div>
      </div>
    </section>

    <section class="pinkbackground">
      <h2>PROGRAM ROSÉ FESTIVAL 2024</h2>
      <div>
        <Program2024 />
      </div>
      <div class="btn pink">PROGRAM</div>
    </section>
    <section>
      <h2>BLIV EN DEL AF DANMARKS STØRSTE ROSÈ FÆLLESSKAB</h2>
      <p>Vi glæder os utroligt meget til at fejre denne fantastiske
        dag sammen med alle jer roséelskere.
      </p>
        <div class="center">
          <video class="hero_movie" controls>
            <source src="../assets/videos/rosefestivalodense_headvideo.mp4" type="video/mp4">
          </video>
        </div>
    </section>
    <section class="pinkbackground">
      <h2>MØD VORES VINUDSTILLERE</h2>
      <p>Vi er stolte af at kunne præsentere Danmarks friskeste
        vinaktører på Odense Rosé Festival 2024.
      </p>
      <Vinudstillere />
      <div class="btn pink">LÆS MERE</div>
    </section>
  </main>
</template>

<style scoped>
  .welcome_container {
    display: flex;
    flex-direction: column;
  }

  @media only screen and (min-width: 960px) { 

    .welcome_container {
      flex-direction: row;
      align-items: center;
      margin-left: 85px;
    }

    .welcome_leftalign {
      width: 50%;
    }

    .welcome_rightalign {
      width: 50%;
      justify-content: flex-end;
  }
}

</style>