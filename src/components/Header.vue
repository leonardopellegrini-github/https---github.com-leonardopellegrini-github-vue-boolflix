<template>
  <div id="head" class="d-flex align-items-center">
    <div class="container d-flex justify-content-between align-item-center">
      <img src="@/assets/img/logo.png" alt="Logo">
      <i class="fas fa-search"></i>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HeaderVue'
}
</script>

<style lang="scss" scoped>
  
  #head{
    height: 15vh;
    background-color: #414141;
    color: white;
    img {
      width: 100px;
    }
  }

</style>