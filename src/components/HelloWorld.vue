<template>
  <button @click="callProps">Button</button>
</template>

<script>
export default {
  name: 'HelloWorld',
  props:{
    func: "",
  },
  data() {
    return {
      msg: 'Welcome to Your Vue.js App',
    };
  },
  methods: {
    callProps: function(){
      console.log(this.func)
      this.func.then((res)=>{
        console.log(res)
      });
    }
  },
  mounted: function(){
    this.callProps()
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
