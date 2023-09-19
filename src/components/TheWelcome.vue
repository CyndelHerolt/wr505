<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  }
})

const symfony = 18
const integration = 16
const reseau = 13
</script>

<template>

  <h2>{{ msg }}</h2>

  <hr>

  <ul>
    <li>Note sur Symfony : {{ symfony }}</li>
    <li>Note en intégration : {{ integration }}</li>
    <li>Note en réseau : {{ reseau }}</li>
  </ul>
</template>
