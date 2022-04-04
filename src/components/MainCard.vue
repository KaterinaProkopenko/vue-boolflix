<template>
    <div class="film-card p-2">
        <div>
            <img :src="poster" alt="Poster">
        </div>
        <p>Title: "{{title}}{{name}}"</p>
        <p :class="(originalTitle == title) ? 'd-none' : ''">Original title: "{{originalTitle}}{{originalName}}"</p>
        <p>Language: <span class="p-1"><img class="language" :src="language" alt="Language"></span></p>
        <p>Vote: "{{vote}}"</p>
    </div>
</template>

<script>
export default {
    name:'MainCard',
    props: ['title', 'originalTitle', 'language', 'vote', 'name', 'originalName', 'poster'],
    methods: {
        /* voteTrasform(number){
            
        } */
    }
}
</script>

<style lang="scss" scoped>
    div.film-card{
        border: 1px solid rgb(255, 106, 0);
        img.language{
            width: 35px;
        }
    }

</style>