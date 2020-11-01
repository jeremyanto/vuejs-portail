<template>
  <div class="container w-4/5 mx-auto mt-4">
    <h1 class="text-lg font-bold">Ma sélection</h1>

    <div v-if="selection.length == 0">
      <p>Aucunes Matière(s) sélectionné</p>
    </div>
    <div v-else>
      <div
        v-for="professeurs in selection"
        :key="professeurs.name" 
        class="border border-black my-4 p-2"
      >
        <h3>{{ professeurs.name }}</h3>
        <span>Matières {{ professeurs.Matière }}</span>
        <img :src="require('../assets/img/' + professeurs.photo)" alt="">
      </div>
    </div>

  </div>
  
</template>

<script>
export default {
  name: "selection-list",
  props: ['selection'],
}
</script>

<style>

</style>