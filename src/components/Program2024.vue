<script setup>
const props = defineProps ([ 'programData' ]);
</script>

<template>
    <div class="program_box">
        <p>{{ programData.time }}</p>
        <p> {{ programData.description }}</p>
        <img :src="programData.image" alt="program billede" />
    </div>
</template>