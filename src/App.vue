<template>
  <div id="app">

    <HelloWorld v-bind:datas="datas"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data(){
    return {datas: []}
  },
  mounted(){
    fetch(`https://covid-19-ao.herokuapp.com/api/general`, {
        method: 'get',
        headers: {
            'Content-Type': 'application/json'
        },

    }).then((response) => response.json())
        .then((res) => {
          this.datas = res.data
        }).catch((error) => {
            console.error(error)
    });
  }
}
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
</style>
