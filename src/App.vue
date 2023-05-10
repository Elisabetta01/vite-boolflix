<script>

  import axios from 'axios';
  import NavComp from './components/NavComp.vue';
  import MainComp from './components/MainComp.vue';
  import { store } from './store';


  export default{
    name: "App",
    components: {
      NavComp,
      MainComp,
    },

    data(){
      return{
        store
      }
    },

    methods: {
      cercaFilm(){
        axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${store.apiKey}&query=${store.testoCerca}`)
        .then((res)=>{
          console.log(res.data.results)
          store.arrayFilm = res.data.results
        })

        axios.get(`https://api.themoviedb.org/3/search/tv?api_key=${store.apiKey}&language=it_IT&query=${store.testoCerca}`)
        .then((res)=>{
          console.log(res.data.results)
          store.arraySerietv = res.data.results
        })

      }
    }
  }
</script>

<template>
  <NavComp @chiamataApi="cercaFilm()"/>
  <MainComp/>
</template>

<style lang="scss">
@use './style/main.scss'
</style>
