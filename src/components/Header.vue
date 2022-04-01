<template>
  <header>
    <div class="input-group mb-3">
        <input v-model="searchString" type="text" class="form-control" placeholder="Search">
        <button @click="$emit('search', searchString)" class="btn btn-primary">Search</button>
    </div>
  </header>
</template>

<script>

export default {
    name: 'indexHeader',
    data: function(){
        return{
            searchString: '',
        }
    },
}
</script>

<style lang="scss" scoped>
    header{
        div{
            width: 400px;
        }
    }

</style>