<template>
  <h1>{{ greet }} {{ name }}</h1>
  <h1>{{ bhtml }}</h1>
  <h2 v-text="channel"></h2>
  <p v-html="bhtml"></p>
  <h2 v-bind:id="headingID">Heading</h2>
  <button v-bind:disabled="isDisabled">Bind</button>
  <h2 class="italic" v-bind:class="status">Status</h2>
  <h2 v-bind:class="isPromoted && 'promoted'">Promoted Movie</h2>
  <h2 v-bind:class="isSoldout ? 'sold-out' : 'new'">Movie soldout?</h2>
  <h2 v-bind:class="['new', 'promoted']">Newly promoted movies</h2>
  <h2 v-bind:class="{
    'promoted': isPromoted,
    'new': !isSoldout,
    'sold-out': isSoldout
  }">Object conditional movie</h2>
  <h2 v-bind:class="[isPromoted && 'promoted', isSoldout ? 'sold-out' : 'new']">Array Conditional Movies</h2>
  <h2 v-bind:style="{
    'color': fontColor,
    'fontSize': headersize,
  }">Inline Styling</h2>
  <h2 v-bind:style="headerStyleObject">Header Style using object</h2>
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
      isDisabled: false,
      status: "success",
      isPromoted: true,
      isSoldout: true,
      fontColor: 'orange',
      headersize: '50px',
      headerStyleObject: {
        color: 'orange',
        fontSize: '50px',
        textDecoration: 'italic',
      }
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

.success {
  text-decoration: underline;
}

.italic {
  color: blueviolet;
}

.promoted {
  font-style: italic;
}

.new {
  color: olivedrab;
}

.sold-out {
  color: red;
}
</style>
