<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <BlaBla :data="data" :year="year" />
    <button @click="loadData()">reload data</button>
    <button @click="increaseYear()">increase year</button>
  </div>
</template>

<script>
import axios from "axios";
import HelloWorld from './components/HelloWorld.vue'
import BlaBla from './components/BlaBla.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    BlaBla,
  },
  data() {
    return {
      data: {},
      year: 2010
    }
  },
  methods: {
    loadData() {
      axios.get('/data.json').then((response) => {
        this.data = response.data;
        console.log("Reloaded!!");
      });
    },
    increaseYear() {
      this.year++;
    }
  },
  mounted() {
    this.loadData();
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
