<template>
  <div id="head" class="d-flex align-items-center">
    <div class="container d-flex justify-content-between align-item-center">
      <img src="@/assets/img/logo.png" alt="Logo">
      <div>
        <i class="fas fa-search"></i>
        <input v-model="ricerca" type="text" placeholder="Cerca qui">
      </div>
      
    </div>
  </div>
</template>

<script>
export default {
  name: 'HeaderVue',
  data(){
    return {
      ricerca: '',
    }
  }
}
</script>

<style lang="scss" scoped>
  
  #head{
    min-height: 15vh;
    background-color: #414141;
    color: white;
    img {
      width: 100px;
    }
  }

</style>