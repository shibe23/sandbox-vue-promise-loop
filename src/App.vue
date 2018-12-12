<template>
  <div id="app">
    <img width="25%" src="./assets/logo.png">
    <HelloWorld @click="callAPI()"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld';

export default {
  name: 'App',
  components: {
    HelloWorld,
  },
  methods: {
    callAPI() {
      return new Promise((resolve) => {
        window.setTimeout(() => {
          console.log('done');
          resolve();
        }, 1000);
        console.log(resolve);
      }).catch((err) => {
        console.log(err);
      });
    },
  },
  mounted() {
    this.callAPI();
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
