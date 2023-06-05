<template>
  <div>
    <pre>
      {{ JSON.stringify(formValues, null, 2) }}
    </pre>
  </div>
  <form @submit.prevent="submitForm">
    <div>
      <label for="name">Name</label>
      <input type="text" id="name" v-model.trim.lazy="formValues.name">
    </div>
    <div>
      <label for="profile">Profile</label>
      <textarea id="profile" v-model="formValues.profileSummary"></textarea>
    </div>
    <div>
      <label for="country">Country</label>
      <select id="country" v-model="formValues.country">
        <option value="">Select a country</option>
        <option value="bangladesh">Bangladesh</option>
        <option value="japan">Japan</option>
        <option value="korea">Korea</option>
      </select>
    </div>
    <div>
      <label for="job-location">Job Location</label>
      <select id="job-location" multiple v-model="formValues.jobLocation">
        <option value="bangladesh">Bangladesh</option>
        <option value="japan">Japan</option>
        <option value="korea">Korea</option>
      </select>
    </div>

    <div>
      <input type="checkbox" id="remoteWork" v-model="formValues.remoteWork" true-value="Yes" false-value="No">
      <label for="remoteWork">Open for remote work?</label>
    </div>

    <div>
      <label>Skill Set</label>
      <input type="checkbox" id="html" v-model="formValues.skillSet" value="html">
      <label for="html">HTML</label>
      <input type="checkbox" id="css" v-model="formValues.skillSet" value="css">
      <label for="css">CSS</label>
      <input type="checkbox" id="javascript" v-model="formValues.skillSet" value="javascript">
      <label for="javascript">Javascript</label>
    </div>

    <div>
      <label>Years of Experience</label>
      <input type="radio" id="0-2" v-model="formValues.yearsOfExperience" value="0-2">
      <label for="0-2">0-2</label>
      <input type="radio" id="3-5" v-model="formValues.yearsOfExperience" value="3-5">
      <label for="3-5">3-5</label>
      <input type="radio" id="6-10" v-model="formValues.yearsOfExperience" value="6-10">
      <label for="6-10">6-10</label>
      <input type="radio" id="6-10" v-model="formValues.yearsOfExperience" value="6-10">
      <label for="6-10">6-10</label>
      <input type="radio" id="10+" v-model="formValues.yearsOfExperience" value="10+">
      <label for="10+">10+</label>
    </div>

    <div>
      <label for="age">Age</label>
      <input @keyup.enter="submitForm" type="number" id="age" v-model.number="formValues.age">
    </div>

    <!-- <div>
      <button>Submit</button>
    </div> -->

  </form>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      formValues: {
        name: '',
        profileSummary: '',
        country: '',
        jobLocation: [],
        remoteWork: "No",
        skillSet: [],
        yearsOfExperience: '',
        age: null,

      }
    }

  },

  methods: {
    submitForm() {
  // event.preventDefault();
  console.log("form value", this.formValues);
    }
  },
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
  /* text-align: center; */
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

input + label {
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
