<template>
  <div>

    <HeaderVue @startSearch="startSearch" />
    <MainVue titleCard="Film" elencoFilm="items" :items="movie"/>
    <MainVue titleCard="Serie TV" elencoFilm="items" :items="tv"/>

  </div>
</template>

<script>

import axios from 'axios'
import 'bootstrap/dist/css/bootstrap.css'
import MainVue from './components/Main.vue'
import HeaderVue from './components/Header.vue'

export default {
  name: 'App',
  components: {
    HeaderVue,
    MainVue
  },

   data(){
    return{
      apiUrlMovie: 'https://api.themoviedb.org/3/search/movie', 
      apiUrlTv: 'https://api.themoviedb.org/3/search/tv',
      apiParams:{
        api_key: 'f16b4e0d1ad76ea4f01b26e4ad97562b',
        language: 'it-IT',
        query: 'rush',
      },
      movie: [],
      tv: [],
      cercaFilm: '',
    }
  },

  mounted(){
    this.getApiMovie();
    this.getApiTv();
  },

  methods:{
      getApiMovie(){
      axios.get(this.apiUrlMovie, {
        params: this.apiParams
      })
      .then(risultato =>{
        console.log(risultato.data)
        this.movie = risultato.data.results;
        console.log(this.movie)
      })
      .catch(errore =>{
        console.log(errore)
      })
    },

    getApiTv(){
      axios.get(this.apiUrlTv, {
        params: this.apiParams
      })
      .then(risultato =>{
        console.log(risultato.data)
        this.tv = risultato.data.results;
        console.log(this.tv)
      })
      .catch(errore =>{
        console.log(errore)
      })
    },

     startSearch(cercaFilm){
      this.apiParams.query=cercaFilm;
      this.getApiMovie(); 
      this.getApiTv(); 
    },
    
  },
 

}
</script>

<style lang="scss">
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

</style>
