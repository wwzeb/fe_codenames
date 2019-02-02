<template>
  <div 
    class="team-score"
    v-bind:class="[color]"
    >
      <h1>{{ teamName }}</h1>
      <h1>{{ score }} / {{ total }}</h1>
  </div>
</template>

<script>
export default {
  name: 'Score',
  props: [
      'teamName',
      'score',
      'color',
      'total'
  ]
}
</script>

<style>
.red {
    color: red;
}
.blue {
    color: blue;
}
</style>
