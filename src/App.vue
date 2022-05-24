<template>
  <div>

    <HeaderVue @startSearch="startSearch" />
    <MainVue elencoFilm="items" :items="movie"/>

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
      apiUrl: 'https://api.themoviedb.org/3/search/movie', 
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

  methods:{
      getApi(){
      axios.get(this.apiUrl, {
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

     startSearch(cercaFilm){
      this.apiParams.query=cercaFilm;
      console.log(this.apiParams);
      this.getApi()
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
