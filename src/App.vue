<template>
  <h2>Volume Tracker (0-20)</h2>
  <h3>Current Volume : {{ volume }}</h3>
  <div>
    <button @click="volume += 2">Increase</button>
    <button @click="volume -= 2">Decrease</button>
  </div>
  <div>
    <input type="text" v-model="movie">
    <input type="text" v-model="movieInfo.title">
    <input type="text" v-model="movieInfo.actor">
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      volume: 0,
      movie: '',
      movieInfo: {
        title: '',
        actor: '',
      },
    }
  },

  methods: {},
  computed: {},
  watch: {
    volume(newValue, oldValue) {
      if (newValue > oldValue && newValue === 16) {
        alert('Listening to a high volume for a long time may damage your hearing');
      }
    },
    movie: {
      handler(newValue) {
        console.log(`Calling API with movie name = ${newValue}`)
      },
      immediate: true
    },
    movieInfo: {
      handler(newValue) {
        console.log(`Calling API with movie title = ${newValue.title} and movie actor = ${newValue.actor}`)
      },
      deep:true
    }
  },
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

label {
  font-weight: bold;
  display: flex;
  margin-bottom: 5px;
}

input+label {
  font-weight: bold;
  display: inline-flex;
  margin-right: 20px;
}

input[type='text'],
textarea,
select {
  display: block;
  width: 400px;
  padding: 6px 12px;
  font-size: 14px;
  line-height: 1.42857143;
  color: #555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 4px;
}
</style>
