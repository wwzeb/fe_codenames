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
    height: 50px;
    display: flex;
    justify-content: center;
    margin: 30px;
    padding: 2em 0;
    border-bottom: 1px solid black;
    border-top: 1px solid black;
}

.button{
    background: #FEDB06;
    color: rgb(59, 0, 0);
    border: none;
    border-radius: 10px;
    margin: 0;
    font-size: 1em;
    font-weight: bold;
    transition: 250ms;
    cursor: pointer;
}

.button:hover,
.button:focus {
  transform: translateX(2px);
  transform: translateY(-1px);
  box-shadow: 1px 2px 3px rgb(180, 180, 180);
  transition: 250ms;
}
</style>
