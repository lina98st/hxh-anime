<script setup lang="ts">
interface Hunter {
    name: string;
    ability: string;
    age: number;
    image: string;
}

defineProps<{ hunter: Hunter }>(); 
</script>

<template>
  <div class="character-card bg-purple-200 rounded-lg shadow-md p-4 flex flex-col items-center">
    <img :src="hunter.image" :alt="hunter.name" class="w-48 h-56 rounded-sm" />
    <h2 class="text-xl font-bold text-center mt-4"> {{ hunter.name }} </h2>
    <p class="text-gray-700 text-center"> Ability: {{ hunter.ability }} </p>
    <p class="text-gray-500 text-center"> Age: {{ hunter.age }} </p>
  </div>
</template>




<style scoped>
.character-card {
  transition: transform 0.3s;
  margin: 3rem;
  padding: 1.5rem;
  color: black;
}

.character-card:hover {
  transform: scale(1.05);
}
</style>
