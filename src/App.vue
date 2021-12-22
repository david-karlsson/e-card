<template>

  <main id="content">  
    <h1>E-card generator </h1>
    
    <addCard/></main>
  

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

h1{
color: #abc;
background-color: rgba(1, 1, 1, 0.5);
padding: 2rem;
border-radius: 5px;
width: 100vw;

}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#content{
  display: flex;
  flex-direction: column;
  align-items: center;
  background:url(https://images.unsplash.com/photo-1591030434469-3d78c7b17820?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1932&q=80) ;
  background-size: cover;
}
</style>
