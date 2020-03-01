<template>
  <div id="app">
    <header class="header">
      <img src="https://assets.change.org/photos/1/gy/bi/hCGybivTSARwGuK-800x450-noPad.jpg?1528973282" alt="Girl in a jacket">
    <h1>English Football Teams</h1>
    </header>
      <team-select :teams="teams"/>
      <team-detail :team="selectedTeam"/>
  </div>
</template>

<script>
import {eventBus} from "./main.js"
import TeamSelect from './components/TeamSelect.vue'
import TeamDetail from './components/TeamDetail.vue'

export default {
  data(){
    return{
      teams:[],
      selectedTeam: null
    }
  },
  components:{
    "team-select": TeamSelect,
    "team-detail":TeamDetail
  },
  mounted(){
    fetch('http://api.football-data.org/v2/teams',{
      headers:{
      'X-Auth-Token':'93fb448d3a40433485767a9bda2a60e9'}
    })
    .then(res=>res.json())
    .then(teams=>this.teams = teams.teams)

    eventBus.$on('team-selected',(team)=>{
        this.selectedTeam=team;
        })
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}


.header{
    height: 80px;
    background: #8888;
    margin-bottom: 20px;
  }


  .header img {
  float: left;
  height: 85px;
  background: blue;
}

.header h1 {
  position: relative;
  top: 18px;
  left: 10px;
}



</style>
