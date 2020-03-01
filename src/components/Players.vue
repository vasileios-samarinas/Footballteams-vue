<template lang="html">
<div>
  <player-data v-for="(player, index) in players" :player="player" :key="index"></player-data>
</div>
</template>

<script>




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
