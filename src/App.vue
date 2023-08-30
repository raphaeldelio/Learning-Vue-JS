<template>
  <div class="top-bar">
    <h1>The Exoplanet Database!</h1>
    <input type="text" placeholder="Search" class="search-bar" />
  </div>

  <div class="card-container">
    <PlanetCard v-for="planet in planets" :key="planet.name" :planet="planet" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import PlanetCard from './components/PlanetCard.vue'; // Add this line
import type { Planet } from './types';
 
export default defineComponent({
  components: { PlanetCard }, // Add this line
  setup() {
    const planets = ref<Planet[]>([
      { name: 'Earth', discoveryYear: 0, lightYearsAway: 0 },
      { name: 'Mars', discoveryYear: 1610, lightYearsAway: 0.000014 },
      { name: 'CoRoT-8b', discoveryYear: 2010, lightYearsAway: 1050 },
      // Add more planets here
    ]);
    return { planets };
  },
});
</script>

<style>
body {
  background-color: #7E88A1;
  display: flex;
  font-family: 'Montserrat', sans-serif; /* Set the font to Montserrat */
}

.card-container {
  display: grid;
  width: 100%;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  gap: 16px;
}

.top-bar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px;
  width: 100%;
}

.search-bar {
  width: 50%;
  border: none;
  border-radius: 20px; /* Rounded corners */
  padding: 8px 16px;
  outline: none;
}
</style>