<template>
   
    <div class="locand">
        <div class="flip-card">
          <div class="flip-card-inner">
            <div class="flip-card-front">
              <img class="copertina" v-if="cardData.poster_path.length != '' " :src="`https://image.tmdb.org/t/p/w342${cardData.poster_path}`" alt="{cardData.title}">
              <img v-else src="../assets/img/logo.png" alt="Logo">
            </div>
            <div class="flip-card-back">
              <h1>{{cardData.title || cardData.name}}</h1> 
              <h3>{{cardData.original_title || cardData.original_name}}</h3> 
              <star-rating :rating="cardData.vote_average" :read-only="true" :star-size="30" :increment="0.01"></star-rating>
              
               <country-flag v-if="cardData.original_language !== 'en'"  :country='cardData.original_language' size='medium'/>
               <img class="inglese" v-else src="../assets/img/england-flag.png" alt="">
            </div>
          </div>
        </div>
    </div>
</template>

<script>
import CountryFlag from 'vue-country-flag';
import StarRating from 'vue-star-rating'

export default {
  name: 'LocandinaVue',

  components: {
    CountryFlag,
    StarRating
  },
  props:{
    cardData: Object,
  },
  

}
</script>

<style lang="scss" scoped>
  .locand{
    height: 250px;
    width: 180px;
    background-color: red;
    margin: 5px;
    float: left;
    .copertina{
    width: 100%;
    height: 100%;
    object-fit: cover;
    overflow: hidden;
    }
    h1{
      font-size: 18px;
    }
    h3{
      font-size: 15px;
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
  text-align: left;
  transition: transform 0.6s;
  transform-style: preserve-3d;
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
}

.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

.flip-card-front, .flip-card-back {
  position: absolute;
  padding: 5px;
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
  background-color: black;
  color: white;
  transform: rotateY(180deg);
}

svg{
  width: 10px;
}

.inglese{
  width: 40px;
  height: 40px;
  margin-top: 10px;
}
  
</style>