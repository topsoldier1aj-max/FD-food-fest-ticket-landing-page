<script setup>
defineProps({
  count: Number
})
</script>

<template>

<nav class="navbar navbar-dark bg-dark">

  <div class="container">

    <span class="navbar-brand">
       Cape Town Food Fest
    </span>

    <span class="badge bg-warning text-dark fs-6">
      Favourites: {{ count }}
    </span>

  </div>

</nav>

<div class="bg-light py-5 text-center">

  <h1>Cape Town Food Fest 2026</h1>

  <p class="lead">
    A weekend of amazing food, talented chefs,
    and live music in the heart of Cape Town.
  </p>

</div>

</template>