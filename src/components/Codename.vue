<template>
  <div class="codename">
      <p class="title">{{ codename }}</p>
  </div>
</template>

<script>
export default {
  name: 'Codename',
  props: [
      'codename'
  ]
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
