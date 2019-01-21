<template>
  <div class="gameboard">
      <div v-for="codename in codenames" :key="codename.codename">
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
    display: flex;
    justify-content: space-between;
    flex-direction: row;
    flex-wrap: wrap;
}
</style>
