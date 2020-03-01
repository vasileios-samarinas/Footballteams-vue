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

.transactions {
  border-collapse: collapse;
  width: 95%;
  margin: 2.5%;
}

.transactions td,th {
  border: 1px solid #ddd;
  padding: 8px;
}

.transactions tr:nth-child(even){background-color: #f2f2f2;}

.transactions tr:hover {background-color: #ddd;}

.transactions th {
  padding-top: 12px;
  padding-bottom: 12px;
  text-align: left;
  background-color: #4CAF50;
  color: white;}

</style>
