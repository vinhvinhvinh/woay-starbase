<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <div class="d-flex justify-content-around">
      <Character v-for="(id,index) in init_ids" :key="index" :id="id"/>
    </div>
  </div>
</template>

<script>
import Character from './components/Character.vue';
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'


export default {
  name: 'App',
  data(){
    return {
      init_ids:[1,2,3],
    }
  },
  components: {
    Character
  },
 
}
</script>

<style>
  *{
    background: #2c3e50;
    color: #fff;
   
  }
#app {
  font-family: cursive;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  
  margin-top: 60px;
}
</style>
