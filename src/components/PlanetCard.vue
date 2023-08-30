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

<style>
.card {
  background-color: #7AB7D1;
  color: #FFFFFF;
  border-radius: 10px;
  padding: 16px;
  width: 200px;
}

.card h2 {
  font-size: 18px;
}

.card p {
  font-size: 14px;
}
</style>