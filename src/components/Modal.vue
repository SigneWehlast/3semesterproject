<script>
  export default {
    name: "Modal",
    methods: {
      show() {
        const modal = document.getElementById("modal");
      },
      hide() {
        const modal = document.getElementById("modal");
        modal.classList.remove("show");
      },
    },
  };
  </script>

<template>
    <div class="modal" id="modal">
      <div class="modal_content">
        <span class="modal_close" @click="hide()">&times;</span>
        <div class="modal_header">
          <h1 class="modal_title">TAK FOR DIN TILMELDING</h1>
        </div>
        <div class="modal_body">
          <div class="feedback">
            <p>
                Tak for at tilmelde dig vores nyhedsbrev!
            </p>
            <p>
                Du er nu med i lodtrækningen om at vinde 2 billetter
            </p>
            <p>
                til Rosé Festival Odense 2024
            </p>
          </div>
        </div>
        <div class="modal_footer">
          <button class="post" @click="hide">Luk</button>
        </div>
      </div>
    </div>
  </template>
  
  
  <style scoped>
  .modal {
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
  
  .modal.show {
    visibility: visible;
    opacity: 1;
  }
  
  .modal.show .modal_content {
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
  
  .modal_header {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 5px 10px;
  }
  
  .modal_title {
    font-weight: normal;
    font-size: 25px;
    align-content: center;
    color: #2D3142;
  }
  
  .modal_close {
    padding: 5px;
    padding-right: 10px;
    cursor: pointer;
    font-size: 25px;
    color: #ED8082;
    display: flex;
    justify-content: flex-end;
  }
  
  .modal_body {
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
  
  .modal_footer {
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
  
  </style>