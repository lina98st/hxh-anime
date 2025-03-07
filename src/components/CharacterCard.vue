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
  <div class="character-card flex flex-col items-center">
    <div class="image-container">
      <img :src="hunter.image" :alt="hunter.name" class="character-image" />
      <div class="image-glow"></div>
    </div>
    <h2 class="character-name mt-4"> {{ hunter.name }} </h2>
    <p class="character-ability"> <span class="label">Ability:</span> {{ hunter.ability }} </p>
    <p class="character-age"> <span class="label">Age:</span> {{ hunter.age }} </p>
  </div>
</template>

<style scoped>
.character-card {
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  margin: 3rem;
  padding: 1.5rem;
  border-radius: 12px;
  background: linear-gradient(135deg, rgba(88, 24, 169, 0.9), rgba(216, 27, 96, 0.9));
  border: 2px solid rgba(255, 255, 255, 0.4);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3), 
              inset 0 0 20px rgba(255, 255, 255, 0.2);
  position: relative;
  overflow: hidden;
  opacity: 0;
  transform: scale(0.9);
  animation: fadeInUp 0.6s ease-out forwards;
}

.character-card::before {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, rgba(255,255,255,0) 70%);
  transform: rotate(30deg);
  pointer-events: none;
}

.image-container {
  position: relative;
  margin-bottom: 10px;
}

.character-image {
  width: 12rem;
  height: 14rem;
  object-fit: cover;
  border-radius: 8px;
  border: 3px solid rgba(255, 255, 255, 0.5);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.4);
  z-index: 1;
  position: relative;
}

.image-glow {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  border-radius: 8px;
  filter: blur(15px);
  opacity: 0;
  background: inherit;
  transition: opacity 0.3s;
  z-index: 0;
}

.character-card:hover .image-glow {
  opacity: 0.7;
}

.character-name {
  font-family: 'Bangers', sans-serif;
  font-size: 1.8rem;
  color: #FFFFFF;
  text-align: center;
  text-shadow: 3px 3px 0 rgba(0, 0, 0, 0.3);
  letter-spacing: 1px;
  margin-bottom: 0.5rem;
}

.character-ability, .character-age {
  font-family: 'Russo One', sans-serif;
  font-size: 1rem;
  color: rgba(255, 255, 255, 0.9);
  text-align: center;
  margin: 0.2rem 0;
  text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.4);
}

.label {
  color: #FFD700;
  font-weight: bold;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px) scale(0.9);
  }
  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}

.character-card:hover {
  transform: translateY(-10px) scale(1.05);
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.5),
              inset 0 0 30px rgba(255, 255, 255, 0.3);
}

.character-card:hover .character-name {
  text-shadow: 0 0 10px rgba(255, 255, 255, 0.8);
}
</style>