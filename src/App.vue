<template>
  <div id="app">
    <Header @search="userSearch"/>
    <Main :userSearchFilms="films"/>

  </div>
</template>

<script>
import axios from "axios"
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
      films: [],
    }
  },
  methods: {
    userSearch(string){
      this.searchString = string;
      if(this.searchString == ''){
        console.warn('La stringa è vuota');
      } else {
        console.log(this.searchString);
        this.searchFilm();
      }
    },

    searchFilm() {
            axios.get('https://api.themoviedb.org/3/search/movie?api_key=579af0003891d434d75f8f646443c140&query=' + this.searchString).then((result) => {
                this.films = result.data.results;
                console.log(this.films);
            })
            .catch((error) => {
                console.log(error);
            })
        }
  }
}
</script>

<style lang="scss">
@import './assets/styles/main-style.scss'

</style>
