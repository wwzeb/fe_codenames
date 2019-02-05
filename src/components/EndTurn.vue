<template>
  <div class="container">
    <button class="button" @click="endTurn">End Turn</button>
  </div>
</template>

<script>
export default {
  name: 'EndTurn',
  props: [
    'endTurn'
  ]
}
</script>

<style>
.container{
    width: 100px;
    height: 50px;
    display: flex;
    justify-content: center;
    margin: 30px;
}

.button{
    margin: 0;
    font-size: 1em;
}
</style>
