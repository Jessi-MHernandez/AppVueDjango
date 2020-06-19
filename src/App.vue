<template>
  <div id="app">
  <!--  <img alt="Vue logo" src="./assets/logo.png"> -->
    <List></List>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import List from './components/List.vue'
//import Detail from './components/Detail.vue'
//import List from './components/Table.vue'

export default {
  name: 'App',
  components: {
    List,
  //  Detail
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
