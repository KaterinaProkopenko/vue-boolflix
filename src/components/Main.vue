<template>
  <main>
      <MainCard v-for="(element, index) in films" :key="index" :title="element.title" :originalTitle="element.original_title" :language="element.original_language" :vote="element.vote_average"/>
       
  </main>
</template>

<script>
import axios from "axios"
import MainCard from "./MainCard.vue"

export default {
    name: 'indexMain',
    components: {
        MainCard,
    },
    props: ['userSearchString'],
    data: function(){
        return{
            films: null,
        }
    },
    methods: {
        searchFilm() {
            axios.get('https://api.themoviedb.org/3/search/movie?api_key=579af0003891d434d75f8f646443c140&query=sinister').then((result) => {
                this.films = result.data.results;
                console.log(this.films);
            })
            .catch((error) => {
                console.log(error);
            })
        }
    },
    created: function() {
        this.searchFilm()
    }
}
</script>

<style lang="scss" scoped>

</style>