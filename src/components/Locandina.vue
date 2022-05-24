<template>
    <!--
    <div class="locand">
      <img :src="`https://image.tmdb.org/t/p/w342${cardData.poster_path}`" alt="cardData.title">
    </div>-->  
    <div class="locand">
        <div class="flip-card">
          <div class="flip-card-inner">
            <div class="flip-card-front">
              <img :src="`https://image.tmdb.org/t/p/w342${cardData.poster_path}`" alt="{cardData.title}">
            </div>
            <div class="flip-card-back">
              <h1>{{cardData.title}}</h1> 
              <p>{{cardData.original_title}}</p> 
              <p>{{cardData.original_language}}</p>
            </div>
          </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'LocandinaVue',
  props:{
    cardData: Object,
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
    h1{
      font-size: 18px;
    }
  }

  .flip-card {
  background-color: transparent;
  height: 250px;
  width: 180px;
  perspective: 1000px;
}

.flip-card-inner {
  position: relative;
  height: 250px;
  width: 180px;
  text-align: center;
  transition: transform 0.6s;
  transform-style: preserve-3d;
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
}

.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

.flip-card-front, .flip-card-back {
  position: absolute;
  height: 250px;
  width: 180px;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}

.flip-card-front {
  background-color: #bbb;
  color: black;
}

.flip-card-back {
  background-color: red;
  color: white;
  transform: rotateY(180deg);
}
  
</style>