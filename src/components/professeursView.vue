<template>
    <img alt="Vue logo" style="width: 150px; margin-top: 3.5em; margin-left: 3em;" src="../assets/img/logo.png" />
    
    <h1 style="margin-left: 560px; font-size: 2.5em; margin-bottom:1em; font-style: oblique;">Liste Des Intervenants</h1>
  
  <div class="flex">
    <div class="w-1/5">
      <selection-box :selection="selection"> </selection-box>
    </div>

    <div class="w-4/5 mt-2">
      <professeurs-card
        v-for="(professeurs, index) in team.professeurs"
        :key="index"
        :professeurs="professeurs"
        @add-professeurs="addprofesseursToSelection"
      >
      </professeurs-card>
    </div>
  </div>
</template>

<script>
import teamData from "../data/profs.json";
import professeursCard from "./professeursCard.vue";
import SelectionBox from "./SelectionBox.vue";

export default {
  name: "professeurs-view",
  components: {
    professeursCard,
    SelectionBox,
  },
  data() {
    return {
      team: teamData,
      selection: [],
    };
  },
  methods: {
    addprofesseursToSelection(professeurs) {
      this.selection.push(professeurs);
      this.$emit("child-event", professeurs);
    },
  },
};
</script>

<style scoped>
</style>