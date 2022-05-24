<template>

  <div id="main">
      
      <div class="container">
        <div class="row align-items-center">
          <div class="col align-self-center">
            <h1>FILM</h1>
            <LocandinaVue v-for="card in items" :key="card.id" :cardData="card"/>
          </div>
          
        </div>
        <div class="row align-items-center">
          <div class="col align-self-center">
            <h1>Serie TV</h1>
            <LocandinaVue v-for="card in items" :key="card.id" :cardData="card"/>
          </div>
          
        </div>
      </div>
    
  </div>
  
</template>

<script>

import LocandinaVue from './Locandina.vue'

export default {
  name: 'MainVue',
  components: {
    LocandinaVue,
  },

  props:{
    items: Array,
    titleCard: String
  },
    
}
</script>

<style lang="scss" scoped>
#main{
  min-height: 85vh;
  background: #141414;
  color: white;
  margin: auto;
  display: block;
}
.contenente{
  width: 90%;
  display: block;
  margin: auto;
  text-align: center;
  height: 85vh;
}

</style>