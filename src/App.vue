<template>
  <img alt="Vue logo" src="./assets/logo.png">

  <!-- Props -->
  <Greet name='Jan' />
  <Greet :name='name' :last-name='lastName' />
  <DateNow />
  <Article id="my-aricle" title="Article Title" :likes='30' :isPublished='true' />

  <!-- Provide/ Inject -->
  <h3>App component {{ name }}</h3>
  <ComponentC />

  <!-- Events -->

  <button @click="showPopup = true">Show Popup</button>
  <Popup v-show="showPopup" @close="closePopup"/>
  <Input v-model="formName" />

  <!-- Slots -->
</template>

<script>
import Greet from './components/Greet';
import DateNow from './components/DateNow';
import Article from './components/Article';
import ComponentC from './components/ComponentC';
import Popup from './components/Popup';
import Input from './components/Input';


export default {
  name: 'App',
  components: {
    Greet, 
    DateNow,
    Article,
    ComponentC,
    Popup,
    Input

  },
  data(){
    return{
      name: 'Max',
      lastName: 'Muller',
      showPopup: false,
      formName: '',
    }
  },
  methods:{
    closePopup(name){
      this.showPopup = false
      console.log('name', name)
    }
  },
  provide(){
    return {
      userName: this.name,
    }
  },
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
