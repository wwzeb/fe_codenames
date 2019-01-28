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
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
}
</style>
