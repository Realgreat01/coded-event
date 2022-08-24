<template>
  <section class="categories-section">
    <h2 class="main-text"> Top Event Categories</h2>
    <h1 class="faded-text faded-category">
      Categories
    </h1>
  </section>
  <div class="top-categories">
    <div v-for="(event, index) in events" :key="index" class="image-container">
      <div class="event-image">
        <img src="../assets/images/icons/dinner.svg" :alt="`icon-${event}`">
      </div>
      <h2 class="event-name">{{event}}</h2>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const events = ref(['Seminars', 'Weddings', 'Burials', 'Parties', 'Charity Outreach'])
</script>
