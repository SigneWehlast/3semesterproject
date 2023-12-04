<script setup>
</script>

<template>
<h2>BILLETINFORMATION</h2>
  <main class="welcome_container">
    <div class="welcome_leftalign">
      
      <p>Billetten koster 499kr. og inkluderer:</p>
      <div class="symbol"><!--symbol-->
        <p>15 slags rosévine fra forskellige forhandlere</p>
      </div>
      <div class="symbol"><!--symbol-->
        <p>Dit helt eget indgraverede Riedel “Vinum Extreme Rose”-glas</p>
      </div>
      <div class="symbol">          
        <img src="../assets/pictures/speech-bubbles-comment-option.png" alt="icon af talebobler" />
        <p>Underholdning & god stemning</p>
      </div>
      <div class="symbol"><!--symbol-->
        <img src="../assets/pictures/fork-and-knife.png" alt="icon af kniv og gafler" />
        <p>Lækker mad & Iskold Rosé</p>
      </div>
      <div class="symbol"><!--symbol-->
        <img src="../assets/pictures/music-player.png" alt="icon af en node" />
        <p>Efterfest med DJ</p>
      </div>
      <p>Et brag af en Rosé Festival afholdes den 
        25. maj 2024 ved Ansgar Anlæg Odense</p>
    </div>

    <div class="welcome_rightalign">
      <div class="center">
      <img src="../assets/pictures/billet.png" class="billet" alt="Ilustration af et par billeter til Rosé Festival Odense" />
      </div>
      <div class="btn blue">KØB BILLET</div>
    </div>
  </main>
</template>

<style scoped>
  .welcome_container {
    display: flex;
    flex-direction: column;
    margin-bottom: 40px;
  }

  h2 {
    text-align: left;
    margin: 20px 0 20px 20px;
  }

  @media only screen and (min-width: 960px) { 

    .welcome_container {
      flex-direction: row;
      align-items: center;
      margin-left: 85px;
      margin-bottom: 75px;
    }

    .welcome_leftalign {
      width: 50%;
    }

    .welcome_rightalign {
      width: 50%;
      justify-content: flex-end;
    }

    h2 {
    margin-left: 105px;
    }

    .billet {
      margin-top: -75px;
    }
}
</style>
