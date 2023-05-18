<script>
     export default {
          name:"FilmComp",
          props: ['propsFilm'],
          
          data(){
               return{

               }
          },

          methods: {
               flag(){
                    let lingua = this.propsFilm.original_language

                    if(lingua == 'en'){
                         lingua = 'GB'
                    } else if(lingua == 'ja'){
                         lingua = 'JP'
                    }else if(lingua == 'fr'){
                         lingua = 'FR'
                    }
                    
                    return lingua
               }

          }
     }
</script>

<template>
     <div>
          <div class="card">
               <img :src="`https://image.tmdb.org/t/p/w500${propsFilm.poster_path}`" class="card-img-top" alt="">
               <div class="card-body">
                    <h5 class="card-title">{{ propsFilm.title }}</h5>
                    <img :src="`https://flagsapi.com/${flag()}/flat/64.png`" class="bandiera">
                    <div>
                         <i class="fa-solid fa-star me-1 stelline-piene" v-for="(element, index) in Math.round(propsFilm.vote_average / 2)"></i>
                         <i class="fa-solid fa-star me-1" v-for="(element, index) in 5 - Math.round(propsFilm.vote_average / 2)"></i>
                    </div>
               </div>
          </div>
     </div>
</template>

<style lang="scss" scoped>
     div{
          .card{
               width: 200px;
               margin: 10px;
               .bandiera{
                    width: 20px;
               }
               .stelline-piene{
                    color: yellow;
               }
          }
     }
</style>