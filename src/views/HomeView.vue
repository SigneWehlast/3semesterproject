<script setup>
import Program2024 from '../components/program2024.vue';
import Vinudstillere from '../components/Vinudstillere.vue';
import HeaderRose from '../components/HeaderRose.vue';

const udforskForsideScroll = () => {
  document.getElementById("forside_scroll").scrollIntoView({ behavior: "smooth" });
    };
</script>

<template>
  <HeaderRose />
  <main>
    <section>
      <div class="hero_forside">
        <h1 class="h1_home">ROSÉ FESTIVAL ODENSE</h1>
        <div class="flex_hero">
          <p class="p_hero">25. maj 2024</p>
          <p class="p_hero">Ansgar Anlæg</p>
        </div>
        <div @click="udforskForsideScroll()" class="btn pink udforsk_forside">UDFORSK</div>
        <i @click="udforskForsideScroll()" class="fa-solid fa-angle-down fa-xl" style="color: #e05254;"></i>
      </div>
    </section>
    <section class="welcome_container_home">
      <div class="welcome_leftalign_home">
        <h2 id="forside_scroll" class="h2_velkommen">VELKOMMEN TIL ROSÉ FESTIVAL ODENSE</h2>
        <p>Odenses største og pinkeste rosé festival har 
          eksisteret siden 2018 og formår hvert år at levere et 
          brag af en festival fyldt med</p>
        
        <div class="symbol">
          <i class="fa-solid fa-champagne-glasses fa-xl" style="color: #e05254;"></i>
          <p>Underholdning</p>
        </div>
        <div class="symbol">
          <i class="fa-solid fa-comments fa-xl" style="color: #e05254;"></i>
          <p>Socialisering & god stemning</p>
        </div>
        <div class="symbol">
          <i class="fa-solid fa-utensils fa-xl" style="color: #e05254;"></i>
          <p>Lækkert mad & Iskold Rosé</p>
        </div>
        <div class="symbol">
          <i class="fa-solid fa-music fa-xl" style="color: #e05254;"></i>
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
      <div class="welcome_rightalign_home">
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
      <a href="/#program">
        <div class="btn pink">PROGRAM</div>
      </a>
    </section>
    <section>
      <h2 class="h2_leftalign">BLIV EN DEL AF DANMARKS STØRSTE ROSÈ FÆLLESSKAB</h2>
      <p class="margin_p">Vi glæder os utroligt meget til at fejre denne fantastiske
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
      <p class="margin_p center_p">Vi er stolte af at kunne præsentere Danmarks friskeste
        vinaktører på Odense Rosé Festival 2024.
      </p>
      <Vinudstillere />
      <div class="btn pink">VINUDSTILLERE</div>
    </section>
  </main>
</template>
