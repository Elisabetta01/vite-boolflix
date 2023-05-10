<script>

     import { store } from '../store';
     import FilmComp from './FilmComp.vue';
     import SerietvComp from './SerietvComp.vue';

     export default {
          name: "MainComp",
          components: {
               FilmComp,
               SerietvComp,
          },
          data(){
               return{
                    store
               }
          }
     }
</script>

<template>
     <main>
          <div id="container-film" class="container w-75 m-auto d-flex flex-wrap justify-content-center">
               <FilmComp v-for="(element, index) in store.arrayFilm" :key="index" :propsFilm="element"/>
          </div>

          <div id="container-film" class="container w-75 m-auto d-flex flex-wrap justify-content-center">
               <SerietvComp v-for="(element, index) in store.arraySerietv" :key="index" :propsSerietv="element"/>
          </div>
     </main>
</template>

<style lang="scss" scoped>

</style>