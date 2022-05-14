<template>
  <div>
    <h2 v-if="num === 0">the number is zero</h2>
    <h2 v-else-if="num > 0">positive number</h2>
    <h2 v-else-if="num < 0">negetive number</h2>
    <h2 v-else>Not a number</h2>

    <template v-if="display">
      <h2>Irshad</h2>
      <h2>Web Dev.</h2>
    </template>
    <h2 v-show="vshow">V Show</h2>
    <h2 v-for="(sport, index) in sports" :key="sport">
      {{ index }} {{ sport }}
    </h2>
    <h2 v-for="fullName in fullNames" :key="fullName">
      {{ fullName.first }} {{ fullName.last }}
    </h2>
    <div v-for="name in hobbiesByName" :key="name">
      <h2>{{ name.name }}</h2>
      <h3 v-for="hobby in name.hobbies" :key="hobby">{{ hobby }}</h3>
    </div>
    <h3 v-for="value in myInfo" :key="value">{{ value }}</h3>
    <h2>Add method - {{ add(2, 3, 4) }}</h2>
    <h2>Multiply method - {{ multiply(10) }}</h2>

  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      baseMultiplier: 5,
      myInfo: {
        name: "Irshad",
        email: "imabbasi@msn.com",
        tlf: "60888636",
      },
      sports: ["cricket", "football", "tennis"],
      fullNames: [
        {
          first: "Irshad",
          last: "Muhammad",
        },
        {
          first: "I",
          last: "Muhammad",
        },
        {
          first: "U",
          last: "Muhammad",
        },
      ],
      hobbiesByName: [
        {
          name: "Irshad",
          hobbies: ["sport", "gaming", "music"],
        },
        {
          name: "I",
          hobbies: ["music", "dance", "travel"],
        },
        {
          name: "U",
          hobbies: ["sport", "gaming"],
        },
      ],
      num: "hi",
      display: false,
      greet: "Hello",
      name: "World",
      vshow: true,
      channel: "<b>v-text</b>",
      headingId: "heading",
      isDisabled: true,
      status: "success",
      isPromoted: true,
      isSoldout: false,
      highlightColor: "orange",
      headerStyleObject: {
        color: "orange",
        fontSize: "50px",
      },
      baseStyleObject: {},
      successStyleObject: {
        color: "green",
        backgroundColor: "lightgreen",
        border: "1px solid black",
      },
      dangerStyleObject: {
        color: "black",
        backgroundColor: "red",
        border: "1px solid black",
      },
    };
  },
  methods: {
    add(a, b, c) {
      return a + b + c;
    },
    multiply: (num) => num * this.baseMultiplier,
  },
};
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
</style>
