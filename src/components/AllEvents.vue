<template>
  <div class="category-section">
    <section>
      <h2 class="faded-text">Top Events</h2>
      <h2 class="all-categories">Popular Events in
        <select name="cities" id="cities">
          <option class="city" v-for="(city, index) in cities" :value="city" :selected="index === 0 ? true: false"
            :key="index">
            {{city}}
          </option>
        </select>
      </h2>
    </section>

    <p class="event-description">Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptatum eos reiciendis
      dolores veritatis vero assumenda perferendis possimus quis. Esse, unde!</p>
    <ul class="check-events">
      <li>All</li>
      <li>Today</li>
      <li>This Weekend</li>
      <li>This Month</li>
      <li>Virtual</li>
    </ul>

    <div class="event-container">
      <div v-for="(event, index) in events" :key="index" class="event-cards" ref="eventBox" style="transition: 1s">
        <img src="../assets/images/pictures/birthday.png" :alt="`flyer ${index+1}`" class="event-flyer">
        <div class="event-details">
          <h2 class="title">{{event.title}}</h2>
          <h2 class="date">{{event.date}}</h2>
          <h2 class="location">{{event.location}}</h2>
        </div>
      </div>
    </div>

    <div class="switch-button">
      <h2 @click="translateBox(50)" class="prev-btn" style="transform: rotate(180deg)"> <img
          src="../assets/images/icons/arrow.svg" alt=""></h2>
      <h2 @click="translateBox(-100)" class="next-btn"> <img src="../assets/images/icons/arrow.svg" alt=""></h2>
    </div>

    <button class=" browse-events">Browse Events</button>
  </div>
</template>

<script setup>
import { onMounted, ref } from 'vue'

const events = ref([])
const initialPosition = ref(0)
const eventBox = ref(null)
const cities = ref(['Lagos', 'Ibadan', 'Abuja', 'Kaduna', 'Onitsha'])
function fillEventObject () {
  for (let i = 0; i < 6; i++) {
    const eventObj = {
      image: 'flyer-1',
      title: 'Funmilayo and Ramota Traditional Wedding',
      date: 'Sat. Jul, 23rd 2:00 PM',
      location: 'Sheba Center, Lagos'
    }
    events.value.push(eventObj)
  }
  return events.value
}

function translateBox (width) {
  initialPosition.value += width
  if (initialPosition.value < 200 && initialPosition.value > -400) {
    for (let i = 0; i < eventBox.value.length; i++) {
      eventBox.value[i].style.transform = `translateX(${initialPosition.value}px)`
    }
  } else if (initialPosition.value > 200) {
    initialPosition.value = 200
  } else {
    initialPosition.value = -400
  }
  console.log(initialPosition.value)
}

onMounted(() => {
  fillEventObject()
})
</script>
