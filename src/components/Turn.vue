<template>
  <div 
    class="turn"
    v-bind:class="[color]"
    >
      <h1>{{ teamName }}'s Turn</h1>
  </div>
</template>

<script>
export default {
  name: 'Turn',
  props: [
      'teamName',
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
