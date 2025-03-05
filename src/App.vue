<script setup lang="ts">
import CharacterList from './components/CharacterList.vue';

const gon = {
  name: "Gon Freecss",
  ability: "Jajanken",
  age: 12
};

</script>

<template>
  <header>
Hunter x Hunter Characters
  </header>

  <main>
<div>
  <CharacterCard :Hunter="gon" />
  </div>
  </main>
</template>

<style scoped>
</style>
