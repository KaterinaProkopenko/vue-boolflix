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
      axios.get('https://api.themoviedb.org/3/search/multi?api_key=579af0003891d434d75f8f646443c140&query=' + this.searchString).then((result) => {
          this.films = result.data.results;
          console.log(this.films);
          this.films.forEach((singleFilm) => {
            switch (singleFilm.original_language) {

              case "en":
                singleFilm.original_language =  "https://images.saymedia-content.com/.image/t_share/MTc0MjU4ODkxNzg4Mzk2NDEy/differences-between-british-and-american-english.png";
                break;

              case "fr":
                singleFilm.original_language =  "https://upload.wikimedia.org/wikipedia/commons/thumb/1/18/Flag_of_France_%28lighter_variant%29.svg/250px-Flag_of_France_%28lighter_variant%29.svg.png";
                break;

              case "es":
                singleFilm.original_language =  "https://upload.wikimedia.org/wikipedia/commons/thumb/9/9a/Flag_of_Spain.svg/2560px-Flag_of_Spain.svg.png";
                break;
              
              case "de":
                singleFilm.original_language =  "https://upload.wikimedia.org/wikipedia/en/thumb/b/ba/Flag_of_Germany.svg/1200px-Flag_of_Germany.svg.png";
                break;

              case "hi":
                singleFilm.original_language =  "https://upload.wikimedia.org/wikipedia/en/thumb/4/41/Flag_of_India.svg/1200px-Flag_of_India.svg.png";
                break;

              case "zh":
                singleFilm.original_language =  "https://cdn.pixabay.com/photo/2020/04/04/11/45/flag-5001937_960_720.jpg";
                break;

              case "ja":
                singleFilm.original_language =  "https://upload.wikimedia.org/wikipedia/commons/thumb/9/9e/Flag_of_Japan.svg/2560px-Flag_of_Japan.svg.png";
                break;

              case "it":
                singleFilm.original_language =  "https://upload.wikimedia.org/wikipedia/en/thumb/0/03/Flag_of_Italy.svg/255px-Flag_of_Italy.svg.png";
                break;

              case "ru":
                singleFilm.original_language =  "https://upload.wikimedia.org/wikipedia/en/thumb/f/f3/Flag_of_Russia.svg/1200px-Flag_of_Russia.svg.png";
                break;

              default:
                singleFilm.original_language = "https://cdn0.iconfinder.com/data/icons/ecommerce-57/100/Ecommerce_RTE-50-512.png"
            }
          })
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
