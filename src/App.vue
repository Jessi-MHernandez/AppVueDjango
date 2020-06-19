<template>
  <div id="app">
    <!--  <img alt="Vue logo" src="./assets/logo.png"> -->
    <Header/>
    <Categories/>
    

      <router-link to="/">Lista</router-link>
      <router-link to="/detail">Detalles</router-link>

     <router-view></router-view>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue'
import Categories from './components/Types.vue'
//import List from './components/List.vue'
//import Detail from './components/Detail.vue'
//import List from './components/Table.vue'

export default {
  name: 'App',
  components: {
  //  List,
    Header,
    Categories
  //  Detail
  }
}
</script>
