<template>
  <div id="app">

    <HeaderVue/>
    <MainVue />
    
  </div>
</template>

<script>
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
