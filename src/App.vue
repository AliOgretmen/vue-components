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
  <Card></Card>
  <Card>Card Content</Card>
  <Card><img src="https://picsum.photos/200" /></Card>
  <Card>
    <template v-slot:header>
      <h3>Header</h3>
    </template>
    <template v-slot:default>
      <img src="https://picsum.photos/200" />
    </template>
    <template v-slot:footer>
      <button>View Details</button>
    </template>
  </Card>
  <NameList>
    <template v-slot:default='slotProps'>
      {{slotProps.firstName}} {{slotProps.lastName}}
    </template>
  </NameList>
  <NameList>
    <template v-slot:default='slotProps'>
      {{slotProps.lastName}}, {{slotProps.firstName}} 
    </template>
  </NameList>

  <!-- Dynamic Components -->
  <button @click="activeTab = 'TabA'">TabA</button>
  <button @click="activeTab = 'TabB'">TabB</button>
  <button @click="activeTab = 'TabC'">TabC</button>
  
  <keep-alive>
    <component :is="activeTab" />
  </keep-alive>

  <!-- <TabA v-if="activeTab == 'TabA'"/>
  <TabB v-if="activeTab == 'TabB'"/>
  <TabC v-if="activeTab == 'TabC'"/> -->
  
  
</template>

<script>
import Greet from './components/Greet';
import DateNow from './components/DateNow';
import Article from './components/Article';
import ComponentC from './components/ComponentC';
import Popup from './components/Popup';
import Input from './components/Input';
import Card from './components/Card';
import NameList from './components/NameList';
import TabA from './components/TabA';
import TabB from './components/TabB';
import TabC from './components/TabC';



export default {
  name: 'App',
  components: {
    Greet, 
    DateNow,
    Article,
    ComponentC,
    Popup,
    Input,
    Card, 
    NameList,
    TabA,
    TabB,
    TabC

  },
  data(){
    return{
      name: 'Max',
      lastName: 'Muller',
      showPopup: false,
      formName: '',
      activeTab: 'TabA'
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

<style >
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
