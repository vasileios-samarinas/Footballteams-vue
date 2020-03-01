<template lang="html">

  <table v-if="players.length > 0" class="football">

    <tr>
      <th>Name</th>
      <th>Nationality</th>
      <th>Position</th>
    </tr>
    <player-data v-for="(player, index) in players" :player="player" :key="index"></player-data>
  </table>


</template>

<script>

import Player from './Player'



export default {
  name:"players-select",
  props:["players"],
  components:{
    "player-data": Player
  }
}
</script>

<style lang="css" scoped>

.football {
  border-collapse: collapse;
  width: 60%;
  margin: auto;
  margin-top: 30px
}


.football tr:nth-child(even){background-color: #f2f2f2;}

.football tr:hover {background-color: #ddd;}

.football th {
  padding-top: 12px;
  padding-bottom: 12px;
  text-align: center;
  background-color: blue;
  color: white;}

  th{font-size:14px;
    height:10px;
  }

</style>
