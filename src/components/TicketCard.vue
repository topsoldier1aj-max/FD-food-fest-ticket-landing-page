<script setup>

const props = defineProps({
  ticket: Object
})

const emit = defineEmits(['toggle-favourite'])

function toggle() {
  emit('toggle-favourite', props.ticket)
}

</script>

<template>

<div
  class="card h-100 shadow-sm"
  :class="ticket.featured ? 'border-warning border-3' : ''"
>

  <div class="card-body">

    <h4 class="card-title text-center">
      {{ ticket.name }} Ticket
    </h4>

    <h3 class="text-center text-success mb-3">
      R{{ ticket.price }}
    </h3>

    <p class="text-center">
      {{ ticket.description }}
    </p>

    <ul class="list-group list-group-flush mb-3">

      <li
        class="list-group-item"
        v-for="benefit in ticket.benefits"
        :key="benefit"
      >
        > {{ benefit }}
      </li>

    </ul>

    <div
      v-if="ticket.featured"
      class="badge bg-warning text-dark mb-3"
    >
      Featured Tier
    </div>

  </div>

  <div class="card-footer bg-white border-0">

    <button
      class="btn btn-outline-danger w-100"
      @click="toggle"
    >

      <span v-if="ticket.favourite">
        ❤️ Favourited
      </span>

      <span v-else>
        🤍 Favourite
      </span>

    </button>

  </div>

</div>

</template>