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
    /* width: 200px;
    height: 100px; */
    padding: 1em;
    display: flex;
    justify-content: center;
    align-items: center;
    border: 1px solid #000;
    margin: 30px;
    box-shadow: 1px 1px 2px gray;
    border-radius: 10px;
    transition: 250ms;
}

.codename:hover,
.codename:focus {
    transform: translateX(3px);
    transform: translateY(-2px);
    box-shadow: 2px 2px 2px gray;
    transition: 250ms;
}

.title {
    margin: 0;
    font-size: 1.8rem;
    text-shadow: 1px 1px 2px rgb(228, 228, 228);
}

.red-background {
    background-color: rgb(209, 1, 1);
    color: rgb(255, 244, 244);
}

.blue-background {
    background-color: rgb(2, 2, 187);
    color: rgb(233, 233, 255);
}

.neutral-background {
    background-color: #f2decd;
    color: #493c30;
}

.black-background {
    background-color: rgb(34, 34, 34);
    color: rgb(255, 245, 245);
}

</style>
