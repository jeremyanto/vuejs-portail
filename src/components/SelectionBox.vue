<template>
  <div class="border border-black text-center m-4 p-4">
    Selection : {{ selection.length }}
    <span v-if="numberSelection">professeurs</span>
    <span v-else>professeurs</span>

    <ul>
      <li v-for="professeurs in selection" :key="professeurs.name">{{ professeurs.name }}</li>
    </ul>

  </div>
  
</template>

<script>
export default {
  name: "selection-box",
  props: ['selection'],
  computed: {
    numberSelection(){
      if(this.selection.length < 2){
        return true
      }
      return false
    }
  }

}
</script>

<style>

</style>