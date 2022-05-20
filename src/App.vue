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


</style>
