<template>
  <div id="app">
    <Header/>
    <!--  <img alt="Vue logo" src="./assets/logo.png"> -->
    <div class="container">
      <div class="row">
        <div class="col-md-4">
          <Categories/>
          <br>
          <Types/>
        </div>
        <div class="col-md-8">
        <router-view></router-view>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header'
import Categories from './components/Categories'
import Types from './components/Types'
//import List from './components/List.vue'
//import Detail from './components/Detail.vue'
//import List from './components/Table.vue'

export default {
  name: 'App',
  components: {
  //  List,
    Header,
    Categories,
    Types
  //  Detail
  }
}
</script>
