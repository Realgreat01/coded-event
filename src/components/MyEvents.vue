<template>
  <div class="my-events">
    <section class="my-events-category">
      <h2> My Events</h2>
    </section>
    <div class="user-events">
      <div v-for="(event, index) in allEvents" :key="index" class="user-events-card">
        <div class="event-image">
          <img src="../assets/images/pictures/birthday.png" :alt="event.title" class="event-flyer">
          <button class="status active" v-if="event.status === 'Active'">{{event.status}}</button>
          <button class="status pending" v-else-if="event.status=== 'Pending'">{{event.status}}</button>
          <button class="status expired" v-else>{{event.status}}</button>
        </div>
        <div class="user-event-details">
          <h2 class="title">{{event.title}}</h2>
          <h2 class="date">{{event.date}}</h2>
          <h2 class="location">{{event.location}}</h2>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const allEvents = ref([
  {
    image: 'flyer-1',
    title: 'Funmilayo and Ramota Traditional Wedding',
    date: 'Sat. Jul, 23rd 2:00 PM',
    status: 'Active',
    location: 'Sheba Center, Lagos'
  },
  {
    image: 'flyer-1',
    title: 'Funmilayo and Ramota Traditional Wedding',
    date: 'Sat. Jul, 23rd 2:00 PM',
    status: 'Pending',
    location: 'Sheba Center, Lagos'
  },
  {
    image: 'flyer-1',
    title: 'Funmilayo and Ramota Traditional Wedding',
    date: 'Sat. Jul, 23rd 2:00 PM',
    status: 'Expired',
    location: 'Sheba Center, Lagos'
  }
])
</script>

<style>

</style>
