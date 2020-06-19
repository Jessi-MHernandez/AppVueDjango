<template>
  <div id="app">

  <!--  <img alt="Vue logo" src="./assets/logo.png"> -->
    <Header/>
    <List></List>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue'
import List from './components/List.vue'
//import Detail from './components/Detail.vue'
//import List from './components/Table.vue'

export default {
  name: 'App',
  components: {
    List,
    Header
  //  Detail
  }
}
</script>
