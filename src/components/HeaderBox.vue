<template>
  <nav>
    <img src="../assets/images/icons/logo-dark.svg" alt="" class="logo">
    <ul class="nav-list">
      <li>Create Event</li>
      <li>My Events</li>
      <li>Wallets</li>
      <li>Pricing</li>
      <li>Contact</li>
    </ul>

    <div class="action-box">
      <div v-if="state.isAutheticated">
        <div class="notification-box">
          <img src="../assets/images/icons/alarm.svg" alt="notification">
          <p class="notification-counter">{{notification}}</p>
        </div>
        <div class="user-box">
          <img src="../assets/images/icons/user.svg" alt="user" @click="state.isAutheticated = false">
        </div>
      </div>

      <div v-else>
        <button @click="state.isAutheticated=true" class="sign-up">Sign Up</button>
        <button class="log-in">Log In <img src="../assets/images/icons/user.svg" alt=""></button>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { state } from '@/composables/auth.js'
import { ref } from 'vue'

const notification = ref(20)
</script>
