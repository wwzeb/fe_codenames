<template>
  <div 
    @click="codenameClick"
    v-bind:class="['codename', show ? `${type}-background` : null]"
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
  data () {
      return {
          show: false
      }
  },
  methods: {
      codenameClick: function () {
        if (this.show) return;
        this.show = true;
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
.red-background {
    background-color: red;
    color: #fff;
}
.blue-background {
    background-color: blue;
    color: #fff;
}
.neutral-background {
    background-color: #f2decd;
    color: #000;
}
.black-background {
    background-color: #000;
    color: #fff;
}
</style>
