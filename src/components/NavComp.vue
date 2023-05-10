<script>

     import { store } from '../store';

     export default {
          name: "NavComp",
          data () {
               return {
                    store
               }
          },
     }
</script>

<template>
     <nav>
          <div class="d-flex justify-content-between px-4">
               <h1 class="text-danger">BOOLFLIX</h1>
               <div>
                    <input type="text" placeholder="Inserisci film e serie tv" v-model="store.testoCerca">
                    <button @click="$emit('chiamataApi')">Cerca</button>
               </div>
          </div>
     </nav>
</template>


<style lang="scss" scoped>
     nav{
          div{
               background-color: rgb(23, 23, 23);
               padding: 10px;
          }
     }
</style>