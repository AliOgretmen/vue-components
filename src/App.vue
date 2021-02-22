<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <Greet name='Jan'/>
  <Greet :name='name' :last-name='lastName'/>
  <DateNow />
</template>

<script>
import Greet from './components/Greet';
import DateNow from './components/DateNow';


export default {
  name: 'App',
  components: {
    Greet, DateNow
  },
  data(){
    return{
      name: 'Max',
      lastName: 'Muller'
    }
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
