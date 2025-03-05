<script setup lang="ts">

interface Hunter {
    name: string;
    ability: string;
    age: number;
    image: string;
}

const props = defineProps<{ hunter: Hunter }>();
</script>

<template>
    <div class="character-card bg-gray-100 rounded-lg shadow-md p-4">
        <img :src="hunter.image" :alt="hunter.name" class="w-32 h-32 rounded-full mx-auto" />
    <h2 class="text-xl font-bold text-center"> {{ hunter.name }} </h2>
    <p class="text-gray-700 text-center"> Abilities: {{ hunter.ability }} </p>
    <p class="text-gray-500 text-center"> Age: {{ hunter.age }} </p>
   </div>
</template>

<style scoped>
.character-card {
transition: transform 0.3s;
}

.character-card:hover {
    transform: scale(1.05);
}
</style>