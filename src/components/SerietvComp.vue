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
          <div class="card position-relative">
               <img :src="`https://image.tmdb.org/t/p/w500${propsSerietv.poster_path}`" class="card-img-top" alt="">
               <div class="card-body info" >
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
               &:hover{
                    min-width: 300px;
               }    
               .info{
                    position: absolute;
                    top: 0;
                    left: 0;
                    right: 0;
                    bottom: 0;
                    opacity: 0;
               &:hover{
                    background-color: rgba(0, 0, 0, 0.6);
                    color: white;
                    opacity: 1;
               }
                    .bandiera{
                         width: 20px;
                    }
                    .stelline-piene{
                         color: yellow;
                    }
               }
          }
     }
</style>