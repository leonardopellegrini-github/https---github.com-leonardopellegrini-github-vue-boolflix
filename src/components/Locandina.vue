<template>
      
    <div class="locand">
      <img :src="`https://image.tmdb.org/t/p/w342${film.poster_path}`" alt="film.title">
    </div>
      
</template>

<script>
export default {
  name: 'LocandinaVue',
  props:{
    film: Object,
  }
}
</script>

<style lang="scss" scoped>

  .locand{
    height: 250px;
    width: 180px;
    background-color: red;
    margin: 5px;
    float: left;
    img{
    width: 100%;
    height: 100%;
    object-fit: cover;
    overflow: hidden;
    }
  }

  

</style>