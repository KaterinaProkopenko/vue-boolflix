<template>
  <main>
    <MainCard v-for="(element, index) in userSearchFilms" :key="index" :poster="element.poster_path" :title="element.title" :originalTitle="element.original_title" :name="element.name" :originalName="element.original_name" :language="element.original_language" :vote="element.vote_average"/> 
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

</style>