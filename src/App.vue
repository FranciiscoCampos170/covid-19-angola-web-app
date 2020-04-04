<template>
  <div id="app">
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">COVID-19</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav mr-auto"> 
    </ul>
  </div>
</nav>

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
  },
  
}
</script>

<style>

</style>
