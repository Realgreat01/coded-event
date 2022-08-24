<template>
  <div class="categories-section">
    <h1 class="main-text"> Top Event Categories</h1>
    <h1 class="faded-text faded-category">
      Categories
    </h1>
  </div>
  <div class="top-categories">
    <div v-for="icon in 5" :key="icon" class="image-container">
      <img src="../assets/images/icons/dinner.svg" :alt="`icon-${icon}`">
    </div>
  </div>
</template>
