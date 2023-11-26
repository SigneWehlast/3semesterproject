<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div>
      <nav>
        <RouterLink to="/">Forside</RouterLink>
        <RouterLink to="/program">Program</RouterLink>
        <RouterLink to="/om">Om Festivalen</RouterLink>
        <RouterLink to="/billet">Billetinformation</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>