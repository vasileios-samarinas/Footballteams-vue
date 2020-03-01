<template lang="html">


<tr>
  <td>{{player.name}}</td>
  <td>{{player.nationality}}</td>
  <td>{{player.position}}</td>
</tr>


</template>

<script>
import {eventBus} from '../main.js'
export default {
  name: 'player-data',
  props: ['player']
}
</script>

<style lang="css" scoped>


</style>
