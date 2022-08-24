<template>
  <div class="benefits-section">
    <h1 class="main-text">Benefits of using Coded Events </h1>
    <h1 class="faded-text faded-benefit">Benefits</h1>
  </div>
  <div v-for="(benefit, index) in benefits" :key="index" class="benefit-container"
    :style="index % 2===0 ? 'flex-direction: row' : 'flex-direction: row-reverse' ">
    <div class="benefit-image">
      <img src="../assets/images/pictures/birthday.png" alt="benefit-1">
    </div>
    <div class="benefit-content">
      <h2 class="numbers">0{{index+1}}</h2>
      <h2 class="title">{{ benefit.title }}</h2>
      <p class="description">{{benefit.description}}</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const benefits = ref([
  {
    title: 'Your Event in a Single BarCode',
    description: 'CodedEvents helps you create beautiful event programmes with lasting experiences'
  },
  {
    title: 'Your Event in a Single BarCode',
    description: 'CodedEvents helps you create beautiful event programmes with lasting experiences'
  },
  {
    title: 'Your Event in a Single BarCode',
    description: 'CodedEvents helps you create beautiful event programmes with lasting experiences'
  }
])
</script>
