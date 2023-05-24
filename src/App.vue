<template>
  <h1>{{ greet }} {{ name }}</h1>
  <h1>{{ bhtml }}</h1>
  <h2 v-text="channel"></h2>
  <p v-html="bhtml"></p>
  <h2 :id="headingID">Heading</h2>
  <button :disabled="isDisabled">Bind</button>
  <h2 class="italic" :class="status">Status</h2>
  <h2 :class="isPromoted && 'promoted'">Promoted Movie</h2>
  <h2 :class="isSoldout ? 'sold-out' : 'new'">Movie soldout?</h2>
  <h2 :class="['new', 'promoted']">Newly promoted movies</h2>
  <h2 :class="{
    'promoted': isPromoted,
    'new': !isSoldout,
    'sold-out': isSoldout
  }">Object conditional movie</h2>
  <h2 :class="[isPromoted && 'promoted', isSoldout ? 'sold-out' : 'new']">Array Conditional Movies</h2>
  <h2 :style="{
    'color': fontColor,
    'fontSize': headersize,
  }">Inline Styling Using object</h2>
  <h2 :style="headerStyleObject">Header Style using object</h2>
  <h2 :style="[successStyleObject, baseStyleObject]">Success Style</h2>
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
        padding: '20px'
      },
      baseStyleObject: {
        fontSize: '50px',
        padding: '10px',
      },
      successStyleObject: {
        color: 'green',
        backgroundColor: 'lightgreen',
        border: '1px solid green',
        padding: '20px'
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
