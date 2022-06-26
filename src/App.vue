<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/><br>
  <input v-model="newToDo" type="text" placeholder="Write your plans!"/>
  <button v-on:click="saveToDo()">Add</button>
  <br><br>
  <template v-bind:key="item.id" v-for="item in ToDos">
    <input type="checkbox" id="checkbox + item.id"/> {{ item }} <br>
  </template>
</template>

<script>
//<input v-model="ToDos" />
//import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  // props is like the constants?? or wat
  props: {
    //newToDo: String
  },
  components: {
    //HelloWorld
  },
  methods: {
    // можно сделать метод по удалению задачи из массива, но я хочу зачёркивать
    saveToDo() {
      console.log(this.newToDo)
      this.ToDos.push(this.newToDo)
      this.newToDo = null
    }
  },
  data() {
    return {
      newToDo : null,
      ToDos : []
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
