<template>
  <div 
    class="team-score"
    v-bind:class="[color]"
    >
      <h1>{{ teamName }}</h1>
      <h1>{{ score }}</h1>
  </div>
</template>

<script>
export default {
  name: 'Score',
  props: [
      'teamName',
      'score',
      'color'
  ]
}
</script>

<style>
.red-team {
    color: red;
}
.blue-team {
    color: blue;
}
</style>
