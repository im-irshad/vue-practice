<template>
  <div>
    <h2>Volume tracker</h2>
    <h3>current Volume - {{ volume }}</h3>
    <div>
      <button @click="volume += 2">Increase</button>
      <button @click="volume -= 2">Decrease</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      volume: 0,
    };
  },
  methods: {
    changeFullName() {
      this.fullName = "Muhammad Irshad";
    },
    getTotal() {
      return this.items.reduce(
        (total, curr) => (total = total + curr.price),
        0
      );
    },
  },
  computed: {
    fullName: {
      get() {
        return `${this.firstName} ${this.lastName}`;
      },
      set(value) {
        const names = value.split(" ");
        this.firstName = names[0];
        this.lastName = names[1];
      },
    },
    total() {
      return this.items.reduce(
        (total, curr) => (total = total + curr.price),
        0
      );
    },
    expensiveItems() {
      return this.items.filter((item) => item.price > 100);
    },
  },
  watch: {
    volume(newValue) {
      if (newValue === 16) {
        alert("Too High volume");
      }
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
