<template>
    <div class="film-card p-2">
        <div>
            <img :src="poster" alt="Poster">
        </div>
        <p>Title: "{{title}}{{name}}"</p>
        <p :class="(originalTitle == title) ? 'd-none' : ''">Original title: "{{originalTitle}}{{originalName}}"</p>
        <p>Language: <span class="p-1"><img class="language" :src="language" :alt="language"></span></p>
        <p>Vote: <span v-html="stars()"></span></p>
        <p></p>
    </div> 
</template>

<script>
export default {
    name:'MainCard',
    props: ['title', 'originalTitle', 'language', 'vote', 'name', 'originalName', 'poster'],
    methods: {
        stars(){
            let star = '<span><i class="fa-solid fa-star"></i></span>';

            if (this.vote <= 2) {
                return star;
            } else if (2 < this.vote && this.vote <= 4) {
                star = star.repeat(2);
                return star;
            } else if (4 < this.vote && this.vote <= 6){
                star = star.repeat(3);
                return star;
            } else if (this.vote > 6 && this.vote <= 8) {
                star = star.repeat(4);
                return star;
            } else if (this.vote > 8 && this.vote <= 10) {
                star = star.repeat(5);
                return star;
            }
        }
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