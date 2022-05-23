<template>
  <div id="main">

      <div class="container contente">
      <LocandinaVue v-for="(film, index) in elencofilm" :key="`film${index}`" :film="film"/>
      </div>
    
  </div>
  
</template>

<script>
import axios from 'axios'
import LocandinaVue from './Locandina.vue'

export default {
  name: 'MainVue',
  components: {
    LocandinaVue
  },
  
  data(){
    return{
      apiUrl: 'https://api.themoviedb.org/3/search/movie?api_key=f16b4e0d1ad76ea4f01b26e4ad97562b&language=it-IT&query=rush',   
      elencofilm: [],
    }
  },
  
  methods:{
    getApi(){
      axios.get(this.apiUrl)
      .then(risultato =>{
        console.log(risultato.data)
        this.elencofilm = risultato.data.results;
        console.log(this.elencofilm)
      })
      .catch(errore =>{
        console.log(errore)
      })
    },
  },

  mounted(){
    this.getApi();
  },

}
</script>

<style lang="scss" scoped>

#main{
  min-height: 85vh;
  background: #141414;
  color: white;
}

.contenente{
  display: block;
  overflow: auto;
}

</style>