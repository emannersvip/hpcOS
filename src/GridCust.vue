<!--
  https://vuejs.org/examples/#grid
-->

<script setup>
import DemoGrid from './HPCGrid.vue'
import { ref } from 'vue'

const searchQuery = ref('')
const gridColumns = ['Logins', 'Schedulers']
const gridData = [
  { Logins: 'pk500', Schedulers: Infinity },
  { Logins: 'server', Schedulers: 9000 },
  { Logins: 'Jackie Chan', Schedulers: 7000 },
  { Logins: 'Jet Li', Schedulers: 8000 }
]
</script>

<template>
  <form id="search">
    Search <input name="query" v-model="searchQuery">
  </form>
  <DemoGrid
    :data="gridData"
    :columns="gridColumns"
    :filter-key="searchQuery">
  </DemoGrid>
</template>
