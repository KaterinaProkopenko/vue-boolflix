<template>
    <div class="film-card m-2 text-light">
        <!-- <div class="w-100 h-100">
            <img class="img-fluid poster" :src="poster" alt="Poster">
        </div> -->
        <h5 ><span class="fw-bold">Title:</span> "{{title}}{{name}}"</h5>
        <h5 :class="(originalTitle == title) ? 'd-none' : ''"><span class="fw-bold">Original title:</span> "{{originalTitle}}{{originalName}}"</h5>
        <h5><span class="fw-bold">Language:</span> <span class="p-1"><img class="language" :src="language" :alt="language"></span></h5>
        <h5><span class="fw-bold">Vote:</span> <span class="star" v-html="stars()"></span></h5>
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
        background-color: rgb(22, 22, 22);
        border: 1px solid white;
        img.language{
            width: 35px;
        }
        span.star{
            color: orange;
        }
    }

    div.film-card,
    img.poster {
        width: 342px;
        height: 465px;
    }

</style>