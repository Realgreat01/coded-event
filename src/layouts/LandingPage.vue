<template>
  <HeaderBox />
  <CarouselBox />
  <BenefitsFeatures v-if="!state.isAutheticated" />
  <EventCategory />
  <MyEvents v-if="state.isAutheticated" />
  <AllEvents />
  <FooterBox />
</template>

<script setup>
import HeaderBox from '@/components/HeaderBox'
import CarouselBox from '@/components/CarouselBox'
import BenefitsFeatures from '@/components/BenefitsFeatures'
import EventCategory from '@/components/EventCategory'
import AllEvents from '@/components/AllEvents'
import FooterBox from '@/components/FooterBox'
import { state } from '@/composables/auth.js'
import MyEvents from '@/components/MyEvents.vue'
</script>
