<template>
  <div class="codename">
      <h1>{{ codename }}</h1>
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
    align-content: center;
    border: 1px solid #000;
    margin: 30px;
}
</style>
