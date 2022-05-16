<template>
  <div>
    <div>
      <pre>
    {{ JSON.stringify(formValues, null, 2) }}
  </pre
      >
    </div>
    <form @submit.prevent="submitForm">
      <div>
        <label for="name">Name</label>
        <input type="text" v-model.trim.lazy="formValues.name" id="name" />
        <label for="profile">Profile Summary</label>
        <textarea
          v-model="formValues.profileSummary"
          id="profile"
          cols="30"
          rows="10"
        ></textarea>
      </div>
      <div>
        <label for="country">Country</label>
        <select id="country" v-model="formValues.country">
          <option value="">select a country</option>
          <option value="Pakistan">Pakistan</option>
          <option value="Denmark">Denmark</option>
          <option value="Sweden">Sweden</option>
        </select>
      </div>
      <div>
        <label for="job-location">Job Location</label>
        <select id="job-location" multiple v-model="formValues.jobLocation">
          <option value="Pakistan">Pakistan</option>
          <option value="Denmark">Denmark</option>
          <option value="Sweden">Sweden</option>
        </select>
      </div>
      <div>
        <label for="remoteWork"> Open to Remote Work?</label>
        <input
          type="checkbox"
          id="remoteWork"
          v-model="formValues.remoteWork"
          true-value="yes"
          false-value="no"
        />
      </div>
      <div>
        <label> Skill Set</label>
        <input
          type="checkbox"
          id="html"
          value="html"
          v-model="formValues.skillSet"
        />
        <label for="html"> HTML</label>
        <input
          type="checkbox"
          id="CSS"
          value="CSS"
          v-model="formValues.skillSet"
        />
        <label for="CSS"> CSS</label>

        <input
          type="checkbox"
          id="JS"
          value="JS"
          v-model="formValues.skillSet"
        />
        <label for="JS"> JS</label>
      </div>
      <div>
        <label>Year of Experience</label>

        <input
          type="radio"
          id="0-2"
          value="0-2"
          v-model="formValues.yearsOfExp"
        />
        <label for="0-2">0-2</label>

        <input
          type="radio"
          id="3-4"
          value="3-4"
          v-model="formValues.yearsOfExp"
        /><label for="3-4">3-4</label>

        <input
          type="radio"
          id="5-8"
          value="5-8"
          v-model="formValues.yearsOfExp"
        /><label for="5-8">5-8</label>
      </div>
      <div>
        <label for="age">Age</label>
        <input
          @keyup.enter="submitForm"
          type="number"
          id="age"
          v-model.number="formValues.age"
        />
      </div>
      <div>
        <button>submit</button>
      </div>
    </form>

  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      formValues: {
        name: "",
        profileSummary: "",
        country: "",
        jobLocation: [],
        remoteWork: "no",
        skillSet: [],
        yearsOfExp: "",
        age: null,
      },
      count: 0,
    };
  },
  methods: {
    submitForm() {
      console.log("form values", this.formValues);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
.underline {
  text-decoration: underline;
}
.promoted {
  font-style: italic;
  color: rebeccapurple;
}
.sold-out {
  color: red;
}
.new {
  color: green;
}
input + label {
  font-weight: bold;
  display: inline-flex;
  margin-right: 20px;
}
label {
  font-weight: bold;
  display: flex;
  margin-bottom: 5px;
}
input[type="text"],
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
}
</style>
