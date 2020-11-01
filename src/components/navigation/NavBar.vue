<template>
  <div class="bg-orange-300 p-2" style="padding-top: 20px; padding-bottom: 20px;">
    <a href="#" @click="changeComponent('professeur-view')">Toutes les matieres</a> | 
    <a href="#" @click="changeComponent('selection-list')">Matière(s) sélectionné</a>
  </div>
</template>

<script>
export default {
  name: "nav-bar",
  methods: {
    changeComponent(value) {
      this.$emit('change-component', value)
    }
  }
}
</script>

<style>

</style>