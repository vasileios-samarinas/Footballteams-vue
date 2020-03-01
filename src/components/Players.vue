<template lang="html">

  <table v-if="players.length > 0">

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
</style>
