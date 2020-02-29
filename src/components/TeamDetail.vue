<template lang="html">
<div v-if="team" id="TeamDetail">
<h2>{{team.name}}</h2>
<p>{{team.venue}}</p>
<p>{{team.clubColors}}</p>


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
