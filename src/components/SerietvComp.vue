<script>
     export default {
           name: "SerietvComp",
           props: ['propsSerietv']
     }
</script>

<template>
     <div>
          <div class="card">
               <img src="" class="card-img-top" alt='propsSerietv.original_title'>
               <div class="card-body">
                    <h5 class="card-title">{{ propsSerietv.name }}</h5>
                    <p class="card-text">{{ propsSerietv.original_language }}</p>
                    <p class="card-text">{{ propsSerietv.vote_average }}</p>
               </div>
          </div>
     </div>
</template>

<style lang="scss" scoped>
          div{
          .card{
               width: 200px;
               height: 200px;
               margin: 10px;
          }
     }
</style>