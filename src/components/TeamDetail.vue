<template lang="html">
<div v-if="team" id="TeamDetail">
<h1>{{team.name}}</h1>
<p>Stadium: {{team.venue}}</p>
<p>Club Colors: {{team.clubColors}}</p>
<img :src="team.crestUrl">

</div>



</template>

<script>

import { eventBus } from '../main.js'

export default {
  name:'team-detail',
  props:['team']
}
</script>

<style lang="css" scoped>
</style>
