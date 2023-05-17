<template>
  <h1>{{ greet }} {{ name }}</h1>
  <h1>{{ bhtml }}</h1>
  <h2 v-text="channel"></h2>
  <p v-html="bhtml"></p>
  <h2 v-bind:id="headingID">Heading</h2>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      greet: 'Hello',
      name: 'Tanvir Shahriar',
      channel: 'Codevolution',
      bhtml: '<i>Calverin</i>',
      headingID: 'heading',
    };
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
