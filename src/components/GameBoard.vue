<template>
  <div class="gameboard">
      <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'GameBoard',
}
</script>

<style>
.gameboard {
    display: grid;
    grid-template-columns: repeat( 5, minmax(250px, 1fr) );
    grid-template-rows: repeat( 5, minmax(75px, 1fr) );
}
</style>
