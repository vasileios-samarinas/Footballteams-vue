<template lang="html">
<h4>{{player.name}}</h4>
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
