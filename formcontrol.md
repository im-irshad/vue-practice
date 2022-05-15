<template>
  <div>
    <div>
      <pre>
    {{ JSON.stringify(formValues, null, 2) }}
  </pre
      >
    </div>
    <form action="">
      <div>
        <label for="name">Name</label>
        <input type="text" v-model="formValues.name" id="name" />
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
      },
      count: 0,
    };
  },
  methods: {
    increment() {
      return (this.count += 1);
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
