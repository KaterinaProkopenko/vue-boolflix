<template>
    <div class="film-card p-2">
        <p>Title: "{{title}}"</p>
        <p>Original title: "{{originalTitle}}"</p>
        <p>Language: <span class="p-1"><img :src="language" alt="Language"></span></p>
        <p>Vote: "{{vote}}"</p>
    </div>
</template>

<script>
export default {
    name:'MainCard',
    props: ['title', 'originalTitle', 'language', 'vote']
}
</script>

<style lang="scss" scoped>
    div.film-card{
        border: 1px solid rgb(255, 106, 0);
        img{
            width: 35px;
        }
    }

</style>