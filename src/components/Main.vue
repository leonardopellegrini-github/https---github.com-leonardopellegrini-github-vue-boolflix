<template>

  <div id="main">
      
      <div class="w90">
      <LocandinaVue v-for="card in items" :key="card.id" :cardData="card"/>
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
}
.contenente{
  width: 90%;
  display: block;
  overflow: auto;
  text-align: center;
  height: 85vh
}
</style>