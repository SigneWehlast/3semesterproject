<script setup>

import Program2024 from '../components/Program2024.vue';
import Vinudstillere from '../components/Vinudstillere.vue';




</script>

<template>
  <main>
    <section>
      <!--hero-->
    </section>
    <section>
      <h2 class="h2_leftalign">VELKOMMEN TIL ROSÉ FESTIVAL ODENSE</h2>
      <p>Odenses største og pinkeste rosé festival har 
        eksisteret siden 2018 og formår hvert år at levere et 
        brag af en festival fyldt med</p>
      
      <div><!--Symbol-->
        <img src="../assets/pictures/champagne-glass.png" alt="icon af glas der skåler" />
        <p>Underholdning</p>
      </div>
      <div><!--Symbol-->
        <img src="../assets/pictures/speech-bubbles-comment-option.png" alt="icon af talebobler" />
        <p>Socialisering & god stemning</p>
      </div>
      <div><!--Symbol-->
        <img src="../assets/pictures/fork-and-knife.png" alt="icon af kniv og gafler" />
        <p>Lækker mad & Iskold Rosé</p>
      </div>
      <div><!--Symbol-->
        <img src="../assets/pictures/music-player.png" alt="icon af en node" />
        <p>Efterfest med DJ</p>
      </div>

      <p>Billetten til festivalen koster 499 kr., hvilket 
        inkluderer 15 slags rosévine fra forskellige 
        forhandlere, en stemningsfuld festivalplads. 
        Derudover får du dit helt eget indgraverede Riedel 
        “Vinum Extreme Rose”-glas, så dine smagninger har 
        de bedste forudsætninger.</p>

      <!--Billede af billet-->
      <div class="btn blue">KØB BILLET</div>
    </section>

    <section class="pinkbackground">
      <h2>PROGRAM ROSÉ FESTIVAL 2024</h2>
      <div>
        <Program2024 />
      </div>
      <div class="btn pink">PROGRAM</div>
    </section>
    <section>
      <h2>BLIV EN DEL AF FÆLLESSKABET</h2>
      <p>Vi glæder os utroligt meget til at fejre denne fantastiske
        dag sammen med alle jer roséelskere.
      </p>
      <!--Video-->
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
