<script setup>
import { ref, computed } from 'vue'
import Header from './components/Header.vue'
import TicketCard from './components/TicketCard.vue'

const tickets = ref([
  {
    id: 1,
    name: "Bronze",
    price: 120,
    description: "Perfect for casual visitors",
    benefits: [
      "General festival entry",
      "Access to food vendors",
      "Live music stage"
    ],
    featured: false,
    favourite: false
  },
  {
    id: 2,
    name: "Silver",
    price: 250,
    description: "Great value for food lovers",
    benefits: [
      "Festival entry",
      "Priority food lines",
      "Chef cooking demos"
    ],
    featured: true,
    favourite: false
  },
  {
    id: 3,
    name: "Gold",
    price: 450,
    description: "VIP experience",
    benefits: [
      "VIP seating area",
      "Free tasting sessions",
      "Meet the chefs lounge"
    ],
    featured: false,
    favourite: false
  }
])

function toggleFavourite(ticket) {
  ticket.favourite = !ticket.favourite
}

const favouriteCount = computed(() => {
  return tickets.value.filter(t => t.favourite).length
})
</script>

<template>

<Header :count="favouriteCount" />

<div class="container mt-5">

  <div class="row g-4">

    <div
      class="col-md-4"
      v-for="ticket in tickets"
      :key="ticket.id"
    >

      <TicketCard
        :ticket="ticket"
        @toggle-favourite="toggleFavourite"
      />

    </div>

  </div>

</div>

</template>
