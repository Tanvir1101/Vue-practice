<template>
  <div></div>

  <h2 v-for="(name, index) in names" :key="name"> {{ index }} {{ name }}</h2>
  <h2 v-for="(name, index) in fullNames" :key="name.first"> {{ index }} {{ name.first}} {{ name.last }}</h2>
  
  <div v-for="actor in actors" :key="actor.actorname">
    <h2>{{ actor.actorname }}</h2>
    <h3 v-for="movie in actor.movies" :key="movie">
      <div v-if="movie.length > 3">
        {{ movie.slice(0,3) }}....
      </div>
      <div v-else>{{ movie }}</div>
    </h3>
  </div>

  <h2 v-for="(value, key, index) in myInfo" :key="value">{{ index }} {{ key }} {{ value }}</h2>

  <!-- <div>
    <h2 v-if="num === 0">This number is zero</h2>
    <h2 v-else-if="num < 0">This number is negative</h2>
    <h2 v-else-if="num > 0">This number is positive</h2>
    <h2 v-else>Not a number</h2>

    <div v-if="display">
      <h2>Tanvir</h2>
      <h2>Shahriar</h2>
      <h2>Vue Js</h2>
    </div>

    <h2 v-show="showElement">Using V-show</h2>
  </div> -->
  <!-- <div>
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
  </div> -->
</template>

<script>


export default {
  name: 'App',
  data() {
    return {

      names: ['Bruce', 'Clark', 'Diana'], //array of strings using v-bind directive

      fullNames:[                         //array of objects using v-bind directive
        {first: 'Bruce', last: 'Wayne'},
        {first: 'Clark', last: 'Kent'},
        {first: 'Princess', last: 'Diana'},
      ],

      actors: [                          //array of arrays using v-bind directive
        {
          actorname: 'Christian Bale',
          movies: ['Batman', 'The prestigw'], 
        },
        {
          actorname: 'Leonardo Di Caprio',
          movies: ['titanic', 'Inception', 'ET'],
        }

      ],

      myInfo: {
        name: 'Tanvir',
        channeL: 'Calverin',
        course: 'vue3',
      }

      
      // num: 'abc',
      // display: true,
      // showElement: true,
      // greet: 'Hello',
      // name: 'Tanvir Shahriar',
      // channel: 'Codevolution',
      // bhtml: '<i>Calverin</i>',
      // headingID: 'heading',
      // isDisabled: false,
      // status: "success",
      // isPromoted: true,
      // isSoldout: true,
      // fontColor: 'orange',
      // headersize: '50px',
      // headerStyleObject: {
      //   color: 'orange',
      //   fontSize: '50px',
      //   textDecoration: 'italic',
      //   padding: '20px'
      // },
      // baseStyleObject: {
      //   fontSize: '50px',
      //   padding: '10px',
      // },
      // successStyleObject: {
      //   color: 'green',
      //   backgroundColor: 'lightgreen',
      //   border: '1px solid green',
      //   padding: '20px'
      // }
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
