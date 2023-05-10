<script>

     import { store } from '../store';
     import FilmComp from './FilmComp.vue';

     export default {
          name: "MainComp",
          components: {
               FilmComp,
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
          <div id="container-film" class="container w-75 m-auto d-flex flex-wrap">
               <FilmComp v-for="(element, index) in store.arrayFilm" :key="index" :propsFilm="element"/>
          </div>
     </main>
</template>

<style lang="scss" scoped>
     main{
          #container-film{

          }
     }
</style>