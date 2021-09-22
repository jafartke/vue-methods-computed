<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" width="25%" />
    <h4>Names starts with 'B'</h4>
    <ul v-for="(name, k) in startsWithB" :key="k">
      <li>{{ name }}</li>
    </ul>
    <h4>Names starts with 'M'</h4>
    <ul v-for="(name, k) in startsWithM" :key="k">
      <li>{{ name }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      names: ["Bob", "Billy", "Mary", "Jane", "Monica"],
    };
  },
  computed: {
    startsWithB() {
      return this.startsWithChar("B");
    },
    startsWithM() {
      return this.startsWithChar("M");
    },
  },
  methods: {
    startsWithChar(whichChar) {
      return this.names.filter((n) => n.startsWith(whichChar));
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
