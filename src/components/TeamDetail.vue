<template lang="html">
<div v-if="team" id="TeamDetail">
<h1>{{team.name}}</h1>
<p>Stadium: {{team.venue}}</p>
<p>Club Colors: {{team.clubColors}}</p>
<img :src="team.crestUrl"  class="logo">
<button v-on:click="showTeamplayers">Show Team Players</button>
  <players-select :players="players"/>
</div>

</template>

<script>

import { eventBus } from '../main.js'
import Players from './Players.vue'


export default {
  data(){
    return{players:[]}
  },
  components:{"players-select": Players},
  name:'team-detail',
  props:['team'],
  methods: {
    showTeamplayers(){
      fetch('http://api.football-data.org/v2/teams/'+this.team.id,{
        headers:{
        'X-Auth-Token':'93fb448d3a40433485767a9bda2a60e9'}
        })
      .then(res=>res.json())
      .then(team=>this.players =team.squad)
      //
      // eventBus.$on('players-selected',(player)=>{
      //     this.selectedPlayer=player;
          }
    }
  }

</script>

<style lang="css" scoped>

.logo{
  height: 200px;
}
</style>
