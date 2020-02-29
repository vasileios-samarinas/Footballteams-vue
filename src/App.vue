<template>
  <div id="app">
  </div>
</template>

<script>


export default {
  data(){
    return{
      footballTeams:[]
    }
  },
  mounted(){
    fetch('http://api.football-data.org/v2/matches',{
      headers:{ 
      'X-Auth-Token':'93fb448d3a40433485767a9bda2a60e9'}
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
  margin-top: 60px;
}
</style>
