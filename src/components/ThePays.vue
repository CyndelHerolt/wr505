<script setup>
import { onMounted, ref } from 'vue'
import axios from 'axios'
import CardPays from "../components/CardPays.vue";

let data = ref('')
const recherche = ref('')
const dataAll = ref('')

defineProps({
  msg: {
    type: String,
    required: true
  }
})

onMounted(async () => {
  const response = await axios.get('https://restcountries.com/v3.1/all')
  data.value = response.data
  dataAll.value = data.value;
})
function filter() {
  data.value = dataAll.value.filter(pays =>
      {
        return pays.name.common.toLowerCase().startsWith(recherche.value.toLowerCase())
      }
  )
}

</script>

<template>

  <h2>{{ msg }}</h2>

  <hr>

  <label for="recherche">Rechercher un pays</label>
  <input v-model="recherche" @keyup="filter" type="text">
  <!--    <p>Message is: {{ recherche }}</p>-->
<!--  <button @click="filter">Filtrer</button>-->

<!--  <h2>Liste de 10 pays</h2>-->
<!--  <ul>-->
<!--    <li v-for=" indice in 10">-->
<!--      pays numéro {{ indice }}-->
<!--      <RouterLink v-bind:to="'/fichepays/'+indice">complément d'info</RouterLink>-->
<!--    </li>-->
<!--  </ul>-->

  <ul v-for="pays in data">
    <card-pays :pays="pays.name.common" :image="pays.flags.svg" :datapays="pays"/>
  </ul>

</template>
