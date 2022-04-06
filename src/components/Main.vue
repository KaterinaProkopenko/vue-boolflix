<template>
  <main class="container-fluid">
    <div class="container h-100 overflow-auto bg-dark">
      <div class="row">
        <div class="col-12 d-flex flex-wrap justify-content-center py-4">
          <MainCard v-for="(element, index) in userSearchFilms" :key="index" :poster="element.poster_path" :title="element.title" :originalTitle="element.original_title" :name="element.name" :originalName="element.original_name" :language="element.original_language" :vote="element.vote_average" :overview="element.overview"/> 
        </div>
      </div>
      
    </div>
    
  </main>
</template>

<script>
import MainCard from "./MainCard.vue"

export default {
    name: 'indexMain',
    components: {
        MainCard,
    },
    props: ['userSearchFilms'],
    methods: {
    }
}
</script>

<style lang="scss" scoped>
  main {
    width: 100%;
    height: calc(100vh - 70px);
    max-height: 100%;
    background-color: rgb(93, 92, 92);
  }

</style>