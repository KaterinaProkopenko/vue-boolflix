<template>
  <div id="app">
    <Header @search="userSearch"/>
    <Main :userSearchString="searchString"/>

  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';


export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  data: function(){
    return{
      searchString: '',
    }
  },
  methods: {
    userSearch(string){
      this.searchString = string;
      console.log(this.searchString);
    }
  }
}
</script>

<style lang="scss">
@import './assets/styles/main-style.scss'

</style>
