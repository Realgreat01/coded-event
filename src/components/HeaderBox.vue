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
        <img src="../assets/images/icons/alarm.svg" alt="notification">
        <img src="../assets/images/icons/user.svg" alt="user" @click="state.isAutheticated = false">
      </div>

      <div v-else>
        <button @click="state.isAutheticated=true" class="log-in">Sign Up</button>
        <button class="log-out">Log in <img src="../assets/images/icons/user.svg" alt=""></button>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { state } from '@/composables/auth.js'
</script>
