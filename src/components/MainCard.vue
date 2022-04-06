<template>
    <div class="film-card m-2 text-light overflow-auto" @mouseover="upHere = true" @mouseleave="upHere = false">
        <div class="w-100 h-100" :class="(upHere) ? 'd-none' : ''">
            <img class="img-fluid poster" :src="poster" alt="Poster">
        </div>
        <div v-show="upHere" class="p-3 h-100 border border-light rounded">
            <h5><span class="fw-bold">Title:</span> "{{title}}{{name}}"</h5>
            <h5 :class="(originalTitle == title) ? 'd-none' : ''"><span class="fw-bold">Original title:</span> "{{originalTitle}}{{originalName}}"</h5>
            <h5><span class="fw-bold my-2">Language:</span> <span><img class="language align-top" :src="language" :alt="language"></span></h5>
            <h5 class="pb-3"><span class="fw-bold">Vote:</span> <span class="star" v-html="stars()"></span></h5>
            <p class="overview-text overflow-auto text-danger">{{overview}}</p>
        </div>
    </div> 
</template>

<script>
export default {
    name:'MainCard',
    props: ['title', 'originalTitle', 'language', 'vote', 'name', 'originalName', 'poster', 'overview'],
    data: function(){
        return {
            upHere : false,
        }
    },
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

        img.language{
            width: 35px;
            height: 22px;
        }

        p.overview-text{
            height: 65%;
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