<template>
  <div id="app">
    <div v-for="(team, index) in results" :key="index">
      <p>{{team.full_name}}</p>
    </div>
  </div>
</template>

<script>

import axios from "axios"

export default {
  name: 'App',

  data(){
    return{
        results:null
    }
  },
  mounted () {
    axios
      .get('https://www.balldontlie.io/api/v1/teams')
      .then(response => (this.results = response.data.data))

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
