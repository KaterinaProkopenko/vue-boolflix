<template>
  <header class="container-fluid bg-gradient">
      <div class="row h-100">
         <div class="col-6 d-flex align-items-center h-100">
             <h2 class="text-uppercase text-danger">boolflix</h2>
         </div>
         <div class="col-6 d-flex align-items-center justify-content-end h-100">
            <div class="input-group input-group-sm ms-input">
                <input v-model.trim="searchString" @keyup.enter="$emit('search', searchString)" type="text" class="form-control" placeholder="Search">
            </div>
         </div>  
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
        width: 100%;
        height: 70px;
        background-color: black;

        div.ms-input{
            width: 350px;
        }
    }

</style>