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
  
  
  <style scoped>
    .konkurrencemodal {
    position: fixed;
    display: flex;
    align-items: center;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.4);
    visibility: hidden;
    opacity: 0;
    transition: opacity 0.4s ease-in-out, visability 0.4s ease-in-out,
      transform 0.4s ease-in-out;
  }
  
  .konkurrencemodal.show {
    visibility: visible;
    opacity: 1;
  }
  
  .konkurrencemodal.show .konkurrencemodal_content {
    visibility: visible;
    opacity: 1;
    transform: scale(1);
    border: 2px solid #ED8082;
  }
  
  .konkurrencemodal_content {
    padding: 10px;
    border-radius: 10px;
    max-width: 600px;
    width: 66%;
    height: auto;
    background: #FCE9E6;
    margin: auto;
    visibility: hidden;
    opacity: 0;
    color: black;
    transform: scale(0.5);
    transition: opacity 0.4s ease-in-out, visability 0.4s ease-in-out,
      transform 0.4s ease-in-out;
  }
  
  .konkurrencemodal_header {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 5px 10px;
  }
  
  .konkurrencemodal_title {
    font-weight: normal;
    font-size: 25px;
    align-content: center;
    color: #2D3142;
  }
  
  .konkurrencemodal_close {
    padding: 5px;
    padding-right: 10px;
    cursor: pointer;
    font-size: 25px;
    color: #ED8082;
    display: flex;
    justify-content: flex-end;
  }
  
  .konkurrencemodal_body {
    padding: 10px;
  }

  label {
    font-weight: bold;
  }
  
  textarea{
    height: 100px;
  }
  
  button {
    background-color: var(--green-primary);
    color: var(--white);
    border-radius: 10px;
    font-size: 16px;
    padding: 8px 18px;
    border: none;
    cursor: pointer;
  }
  
  select:focus {
    outline: none;
    border-color: #007bff;
  }
  
  .konkurrencemodal_footer {
    display: flex;
    align-items: center;
    padding-bottom: 20px;
  }
  
  .post {
    margin: 15px;
    padding: 10px 30px;
    cursor: pointer;
    color: #f2f2f2;
    background-color: #ED8082;
  }

.input_modal {
    padding: 0 20px;
}

.feedback p {
    line-height: 25px;
  }
  

  /*
  .konkurrencemodal {
    position: fixed;
    display: flex;
    align-items: center;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.4);
    visibility: hidden;
    opacity: 0;
    transition: opacity 0.4s ease-in-out, visability 0.4s ease-in-out,
      transform 0.4s ease-in-out;
  }
  
  .konkurrencemodal_content {
    background-color: white;
    display: flex;
    flex-direction: column;
  }

  .konkurrencemodal.show {
    visibility: visible;
    opacity: 1;
  }
  
  .konkurrencemodal.show .modal_content {
    visibility: visible;
    opacity: 1;
    transform: scale(1);
    border: 2px solid #ED8082;
  }
  
  .modal_content {
    padding: 10px;
    border-radius: 10px;
    max-width: 600px;
    width: 66%;
    height: auto;
    background: #FCE9E6;
    margin: auto;
    visibility: hidden;
    opacity: 0;
    color: black;
    transform: scale(0.5);
    transition: opacity 0.4s ease-in-out, visability 0.4s ease-in-out,
      transform 0.4s ease-in-out;
  }
  
  .konkurrencemodal_header {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 5px 10px;
  }
  
  .konkurrencemodal_title {
    font-weight: normal;
    font-size: 25px;
    align-content: center;
    color: #2D3142;
  }
  
  .konkurrencemodal_close {
    padding: 5px;
    padding-right: 10px;
    cursor: pointer;
    font-size: 25px;
    color: #ED8082;
    display: flex;
    justify-content: flex-end;
  }
  
  .konkurrencemodal_body {
    padding: 10px;
  }

  label {
    font-weight: bold;
  }
  
  textarea{
    height: 100px;
  }
  
  button {
    background-color: var(--green-primary);
    color: var(--white);
    border-radius: 10px;
    font-size: 16px;
    padding: 8px 18px;
    border: none;
    cursor: pointer;
  }
  
  select:focus {
    outline: none;
    border-color: #007bff;
  }
  
  .konkurrencemodal_footer {
    display: flex;
    justify-content: center;
    align-items: center;
    padding-bottom: 20px;
  }
  
  .post {
    margin: 15px;
    padding: 10px 30px;
    cursor: pointer;
    color: #f2f2f2;
    background-color: #ED8082;
  }

.feedback {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.feedback p {
    line-height: 25px;
  }
  */
  </style>