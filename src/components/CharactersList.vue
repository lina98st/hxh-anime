<script setup lang="ts">
import { ref } from "vue";
import CharacterCard from './CharacterCard.vue';
import characters from '../data/characters.json'; 

interface Hunter {
  name: string;
  ability: string;
  age: number;
  image: string;
}

const characterList = ref<Hunter[]>(characters);
</script>

<template>
  <div class="grid grid-cols-1 md:grid-cols-3 gap-6 p-4">
    <CharacterCard 
    v-for="(hunter, index) in characterList" 
    :key="index" 
    :hunter="hunter"  
    />
  </div>
</template>

<style scoped>
.grid {
  max-width: 1200px;
  margin: auto;
}
</style>

