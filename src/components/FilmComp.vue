<script>
     export default {
          name:"FilmComp",
          props: ['propsFilm']  
     }
</script>

<template>
     <div>
          <div class="card">
               <img src="" class="card-img-top" alt='propsFilm.original_title'>
               <div class="card-body">
                    <h5 class="card-title">{{ propsFilm.title }}</h5>
                    <p class="card-text">{{ propsFilm.original_language }}</p>
                    <p class="card-text">{{ propsFilm.vote_average }}</p>
               </div>
          </div>
     </div>
</template>

<style lang="scss" scoped>
     div{
          .card{
               width: 200px;
               margin: 10px;
          }
     }
</style>