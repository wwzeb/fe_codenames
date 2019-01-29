<template>
  <div 
    class="codename"
    @click="codenameClick"
    >
      <p class="title">{{ codename }}</p>
  </div>
</template>

<script>
export default {
  name: 'Codename',
  props: [
      'codename',
      'type',
      'increaseScore'
  ],
  methods: {
      codenameClick: function () {
        // do stuff localy to this component

        // call function being passed down from parent to increase global score
        this.increaseScore(this.type);
      },
  }
}
</script>

<style>
.codename {
    width: 200px;
    height: 100px;
    display: flex;
    justify-content: center;
    align-items: center;
    border: 1px solid #000;
    margin: 30px;
}
.title {
    margin: 0;
    font-size: 2em;
}
</style>
