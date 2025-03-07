<script setup lang="ts">
import CharactersList from './components/CharactersList.vue'; // 
</script>

<template>
  <header>
    <h1>Hunter x Hunter Characters</h1>
  </header>

  <main>
    <CharactersList /> 
  </main>
</template>

<style scoped>
header {
  text-align: center;
  font-size: 1.5rem;
  font-weight: bold;
  margin: 1rem;
}

header h1 {
font-family: 'Bangers', 'Russo One', sans-serif;
  font-size: 3rem;
  font-weight: 800;
  text-align: center;
  color: #FF355E; 
  text-transform: uppercase;
  letter-spacing: 2px;
  text-shadow: 3px 3px 0 #2E2EFE, 
               6px 6px 0 rgba(0, 0, 0, 0.3); 
  transform: skew(-5deg); 
  background: linear-gradient(to bottom, #FF355E, #FF00CC);
  -webkit-background-clip: text;
  background-clip: text;
  /* color: transparent; */ /* Auskommentiert, damit es überall funktioniert */
  animation: pulse 2s infinite alternate; /* Pulsierender Effekt */
}

@keyframes pulse {
  from {
    filter: drop-shadow(0 0 5px #FF355E);
  }
  to {
    filter: drop-shadow(0 0 15px #FF355E);
  }
}

</style>
