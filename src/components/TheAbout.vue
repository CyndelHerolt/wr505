<script setup>
import { ref } from 'vue'
defineProps({
  msg: {
    type: String,
    required: true
  }
})
const awesome = ref(true);
const items = [{ message: 'Foo' }, { message: 'Bar' }]
</script>

<template>

  <h2>{{ msg }}</h2>

  <hr>

  <h3>Tests</h3>

  <button @click="awesome = !awesome">Basculer</button>
  <ul>
    <li v-if="awesome ">super</li>
    <li v-else>pas super</li>
  </ul>

  <hr>

  <h3>Boucles</h3>

  <ul>
    <li v-for="item in items">
      {{ item.message }}
    </li>
  </ul>
</template>
