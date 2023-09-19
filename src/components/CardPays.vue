<script setup>
defineProps(['pays', 'capitale', 'image', 'datapays'])
</script>

<template>
  <ul>
    <li>Pays : {{ pays }}</li>
    <li><img :src="image" alt="drapeau" style="width: 100px"></li>
    <!--    <li>Data : {{ datapays }}</li>-->
    <routerLink :to="'/fiche-pays/'+pays">complément d'info</routerLink>
  </ul>
</template>