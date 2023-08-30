<template>
  <div class="top-bar">
    <h1>The Exoplanet Database!</h1>
    <input type="text" v-model="searchQuery" placeholder="Search" class="search-bar"/> <!-- New search bar -->
  </div>
  <div class="card-container">
    <PlanetCard v-for="planet in filteredPlanets" :key="planet.name" :planet="planet" /> <!-- Use filtered planets -->
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, computed } from 'vue';
import PlanetCard from './components/PlanetCard.vue';
import type { Planet } from './types';

export default defineComponent({
  components: { PlanetCard },
  setup() {
    const planets = ref<Planet[]>([
      { name: 'Xenon', discoveryYear: 2042, lightYearsAway: 4.2 },
      { name: 'Yara', discoveryYear: 2050, lightYearsAway: 5.3 },
      { name: 'Zeta', discoveryYear: 2060, lightYearsAway: 6.4 },
      { name: 'Alpha', discoveryYear: 2070, lightYearsAway: 7.5 },
      { name: 'Beta', discoveryYear: 2080, lightYearsAway: 8.6 },
      { name: 'Gamma', discoveryYear: 2090, lightYearsAway: 9.7 },
      { name: 'Delta', discoveryYear: 2100, lightYearsAway: 10.8 },
      { name: 'Epsilon', discoveryYear: 2110, lightYearsAway: 11.9 },
      { name: 'Eta', discoveryYear: 2130, lightYearsAway: 14.1 },
      { name: 'Theta', discoveryYear: 2140, lightYearsAway: 15.2 },
      { name: 'Iota', discoveryYear: 2150, lightYearsAway: 16.3 },
      { name: 'Kappa', discoveryYear: 2160, lightYearsAway: 17.4 },
      { name: 'Lambda', discoveryYear: 2170, lightYearsAway: 18.5 },
      { name: 'Mu', discoveryYear: 2180, lightYearsAway: 19.6 },
      { name: 'Nu', discoveryYear: 2190, lightYearsAway: 20.7 },
      { name: 'Xi', discoveryYear: 2200, lightYearsAway: 21.8 },
      { name: 'Omicron', discoveryYear: 2210, lightYearsAway: 22.9 },
      { name: 'Pi', discoveryYear: 2220, lightYearsAway: 24 },
      { name: 'Rho', discoveryYear: 2230, lightYearsAway: 25.1 },
    ]);

    const searchQuery = ref(''); // New ref for search query

    const filteredPlanets = computed(() => { // New computed property
      return planets.value.filter(planet =>
        planet.name.toLowerCase().includes(searchQuery.value.toLowerCase())
      );
    });

    return { filteredPlanets, searchQuery }; // Return searchQuery and filtered planets instead of all planets
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