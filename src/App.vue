<script lang="ts">
import { defineComponent, ref } from 'vue';
import type { Planet } from './types'; // Adjust the path to match the location of your types file

export default defineComponent({
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

<template>

</template>

<style scoped>

</style>