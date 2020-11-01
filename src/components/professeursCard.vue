<template>
  <div 
    class="border m-2 p-2 flex justify-between"
    :class="healthStyle"
  >
    <div>
      <h1 class="text-lg font-bold">{{ professeursName }}</h1>
      <p> {{ professeursMatièreUp }} </p>
    </div>
    <base-button
      text="Sélectionner"
      @click="addToSelection"
    >
    </base-button>
  </div>
</template>

<script>
export default {
  name: "professeurs-card",
  props: ['professeurs'],
  computed: {
    professeursName(){
      if(this.professeurs.name.split('.').length > 1){
        return this.professeurs.name.split('.')[1]
      }
      return this.professeurs.name;
    },
    professeursMatièreUp(){
      return this.professeurs.matière.toUpperCase()
    },
    isInjured() {
      if(this.professeurs.health == "out"){
        return true
      }
      return false
    },
    healthStyle() {
      return { 
        'bg-gray-600': this.isInjured, 
        'border-white': this.isInjured, 
        'border-black': !this.isInjured 
      }
    }
  },
  methods: {
    addToSelection() {
      this.$emit('add-professeurs', this.professeurs)
    }
  }
}
</script>

<style scoped>

</style>