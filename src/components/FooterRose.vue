<script setup>
    import { ref } from 'vue';

    const emit = defineEmits(['submitted']);

    const name = ref('');
    const email = ref('');

    const onSubmitForm = () => {
        fetch('https://semesterproject-c7cbb-default-rtdb.europe-west1.firebasedatabase.app/submit.json', {
            method: 'POST',
            body: JSON.stringify({
                name: name.value,
                email: email.value
            })
        })
        .then((res) => {
            emit('submitted');
            resetForm();
        });
    };

    const resetForm = () => {
        name.value = '';
        email.value = '';
    }

</script>
<template>
    <footer class="pinkbackground">
        <div class="footer_follow">
            <p class="p_centeralign bold">Følg os</p>
            <!--symboler-->
            <p class="p_centeralign">Tilmeld vores nyhedsbrev</p>
            <form class="submitform" v-on:submit.prevent="onSubmitForm">
                <input class="inputform" type="text" v-model="name" placeholder="Navn" />
                <input class="inputform" type="email" v-model="email" placeholder="Email" />
            
                <button type="submit" class="btn pink btn_form">TILMELD</button>
            </form>
        </div>
        <div class="footer_flexcontainer">
            <div class="footer_info">
                <p>Rosévinfestival.dk ApS</p>
                <p>CVR-nr. 29124939</p>
                <p>Carl Plougs Vænge 3</p>
                <p>5230 Odense M</p>
                <p>Tlf. 60523079</p>
            </div>
            <div class="footer_find">
                <p>Køb billet</p>
                <p>Om festivalen</p>
                <p>Bliv frivillig</p>
                <p>Ofte stillede spørgsmål</p>
                <p>Find vej</p>
            </div>
        </div>
    </footer>
    </template>