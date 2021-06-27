<template>
  <img alt="Vue logo" src="./assets/logo.png">
  
</template>

<script>
import axios from "axios";
export default {
  data(){
    return{
      paises:[]
    }
  },
  methods:{
    initialize() {
      axios.get("https://raw.githubusercontent.com/owid/covid-19-data/b2ba285bd7c6cea38ddabef8d0cf4654bded4307/public/data/ecdc/owid-covid-data-last-ecdc.json")
              .then((response)=>{
                this.paises=response.data;
                console.log(this.paises[0]);
              });
        }
      },
  mounted() {
    this.initialize()
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
