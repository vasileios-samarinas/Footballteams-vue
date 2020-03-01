<template lang="html">
  <div v-if="team" id="TeamDetail">
    <div>
      <h1>{{team.name}}</h1>
      <p>Stadium: {{team.venue}}</p>
      <p>Club Colors: {{team.clubColors}}</p>
      <img :src="team.crestUrl"  class="logo">
    </div>
    <button v-on:click="showTeamplayers" class="primary_button">Show Team Players</button>
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

      }
    }
  }

  </script>

  <style lang="css" scoped>

  .logo{
    height: 200px;
  }

  .primary_button{
    color:white;
    border-radius: 10px;
    text-shadow: 0 1px 1px rgba(0, 0, 0, 0.2);
    background: rgb(202, 60, 60);
  }
  </style>
