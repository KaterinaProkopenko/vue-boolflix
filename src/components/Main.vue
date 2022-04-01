<template>
  <main>
      <MainCard/>
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
    created: function() {
        axios.get('...').then((result) => {
            console.log(result);
        })
        .catch((error) => {
            console.log(error);
        })
    }
}
</script>

<style lang="scss" scoped>

</style>