<template>
  <div class="gameboard">
      <div v-for="codename in codenames">
          <codename :codename="codename.codename"></codename>
      </div>
  </div>
</template>

<script>
import Codename from './Codename';

export default {
  name: 'GameBoard',
  components: {
      Codename
  },
  props: [
      'codenames'
  ]
}
</script>

<style>
.gameboard {
    width: 90%;
    border: 1px solid black;
    display: flex;
    flex-wrap: wrap;
}
</style>
