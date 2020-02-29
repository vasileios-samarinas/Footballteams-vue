<template lang="html">
  <select @change="handleChange" v-model="selectedTeam">
    <option v-for="team in teams" :value="team">{{team.name}}</option>
  </select>
</template>

<script>
import {eventBus} from "../main.js"


export default {
name:"team-select",
props:["teams"],
data(){
  return {
    selectedTeam:{}
  }
},
methods:{
  handleChange: function(){
    eventBus.$emit("team-selected",this.selectedTeam)
  }
}
}
</script>

<style lang="css" scoped>
</style>
