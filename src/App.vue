<template>
  <div>

    <HeaderVue/>
    <MainVue />

  </div>
</template>

<script>

import 'bootstrap/dist/css/bootstrap.css'
import MainVue from './components/Main.vue'
import HeaderVue from './components/Header.vue'

export default {
  name: 'App',
  components: {
    HeaderVue,
    MainVue
  }
}
</script>

<style lang="scss">
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

</style>
