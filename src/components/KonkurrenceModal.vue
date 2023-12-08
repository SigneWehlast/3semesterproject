<script>
  export default {
    name: "KonkurrenceModal",
    methods: {
      show() {
        const modal = document.getElementById("modalOne");
      },
      hide() {
        const modal = document.getElementById("modalOne");
        modal.classList.remove("show");
      },
    },
  };

  
  </script>

<template>
    <div class="konkurrencemodal" id="modalOne">
      <div class="konkurrencemodal_content">
        <span class="konkurrencemodal_close" @click="hide()">&times;</span>
        <div class="konkurrencemodal_header">
          <h1 class="konkurrencemodal_title">VIND 2 BILLETTER</h1>
        </div>
        <div class="konkurrencemodal_body">
          <div class="feedback">
            <p>
                Tilmeld vores nyhedsbrev og vær med i lodtrækningen om 2 gratis billetter 
            til Rosévin Festival Odense 2024.
            </p>
            <form class="input_modal" v-on:submit.prevent="onSubmitForm">
                <input class="inputform" type="text" v-model="name" placeholder="Navn" />
                <input class="inputform" type="email" v-model="email" placeholder="Email" />
            </form>
          </div>
        </div>
        <div class="konkurrencemodal_footer">
          <button class="post" @click="hide">TILMELD</button>
        </div>
      </div>
    </div>
  </template>