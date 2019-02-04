<template>
  <div class="container">
    <button class="button" @click="endTurnClick">End Turn</button>
  </div>
</template>

<script>
export default {
  name: 'EndTurn',
  props: [
    'endTurn'
  ],
  methods: {
      endTurnClick: function() {
          this.endTurn();
      }
  }
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
