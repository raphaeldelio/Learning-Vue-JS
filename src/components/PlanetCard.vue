<template>
    <div class="card">
      <h2>{{ planet.name }}</h2>
      <p>Year of Discovery: {{ planet.discoveryYear }}</p>
      <p>Light Years Away: {{ planet.lightYearsAway }}</p>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import type { Planet } from '../types'; 

export default defineComponent({
  props: {
    planet: {
      type: Object as () => Planet,
      required: true,
    },
  },
});
</script>