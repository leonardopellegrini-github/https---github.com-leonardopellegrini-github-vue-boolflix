<template>
  <div id="main">
    <div class="container p-3">
      <LocandinaVue />
    </div>
    
  </div>
  
</template>

<script>
import LocandinaVue from './Locandina.vue'

export default {
  name: 'MainVue',
  components: {
    LocandinaVue
}
}
</script>

<style lang="scss" scoped>
#main{
  height: 85vh;
  background: #141414;
  color: white;
}

</style>