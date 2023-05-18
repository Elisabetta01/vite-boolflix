<script>
     export default {
          name: "SerietvComp",
          props: ['propsSerietv'],
          
          data(){
               return{

               }
          },
          methods: {
               flag(){
                    let lingua = this.propsSerietv.original_language

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
               <img :src="`https://image.tmdb.org/t/p/w500${propsSerietv.poster_path}`" class="card-img-top" alt="">
               <div class="card-body">
                    <h5 class="card-title">{{ propsSerietv.name }}</h5>
                    <img :src="`https://flagsapi.com/${flag()}/flat/64.png`" class="bandiera">
                    <div>
                         <i class="fa-solid fa-star me-1 stelline-piene" v-for="(element, index) in Math.round(propsSerietv.vote_average / 2)"></i>
                         <i class="fa-solid fa-star me-1" v-for="(element, index) in 5 - Math.round(propsSerietv.vote_average / 2)"></i>
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