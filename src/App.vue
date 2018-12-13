<template>
  <div id="app">
    <img width="25%" src="./assets/logo.png">
    <HelloWorld :func="someActions"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    HelloWorld,
  },
  methods: {
    async someActions() {
      await this.callAPI()
    },
    async callAPI(){
      await axios.get("http://localhost:8080/")
        .then((res) => {
          console.log(res);
          return res
        })
        .catch((error) => {
          console.log(error);
        })
    }
  },
  mounted() {
    // this.callAPI().then((res)=>{
    //   console.log(res)
    // });
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
