<template>
  <div>
    <h2>Fullname - {{ firstName }} {{ lastName }}</h2>
    <h2>Fullname - {{ fullName }}</h2>
    <button @click="changeFullName">Change FullName</button>
    <h2>
      <button @click="items.push({ id: 4, title: 'keyboard', price: 50 })">
        add to cart
      </button>
    </h2>
    <h2>
      Total -
      {{ total }}
    </h2>
    <h2>
      Total m-
      {{ getTotal() }}
    </h2>

    <div v-for="item in items" :key="item.id">
      <h2 v-if="item.price > 100">{{ item.title }}</h2>
    </div>

    <div v-for="item in expensiveItems" :key="item.id">
      <h2>{{ item.title }}</h2>
    </div>

  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      firstName: "Bruce",
      lastName: "wayne",
      country: "",
      items: [
        {
          id: 1,
          title: "TV",
          price: 100,
        },
        {
          id: 1,
          title: "mobile",
          price: 200,
        },
        {
          id: 1,
          title: "laptop",
          price: 300,
        },
      ],
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
