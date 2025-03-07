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
  margin-bottom: 20px;
}
</style>
