<template>

  <div>  <addCard/></div>
  

</template>

<script>

import addCard from './components/addCard.vue'
export default {
  name: 'App',
  components: {
  
    addCard
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
