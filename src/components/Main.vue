<template>
  <div id="main">
    <div class="container p-3">
      <LocandinaVue />
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
      apiUrl: 'https://api.themoviedb.org/3/movie/550?api_key=f16b4e0d1ad76ea4f01b26e4ad97562b&language=it-',
    }
  },
  
  methods:{
    getApi(){
      axios.get(this.apiUrl)
      .then(r =>{
        console.log(r.data)
        this.elencofilm = r.data.response;
      })
      .catch(e =>{
        console.log(e)
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
  height: 85vh;
  background: #141414;
  color: white;
}

</style>