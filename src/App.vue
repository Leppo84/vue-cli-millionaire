<template>
  <div id="app">
    <header>
      <!-- <h1>
        Who wants to be a millionaire?
      </h1> -->
      <img class="logo" alt="Millionaire logo" src="./assets/logo.png">
    </header>
    <ContainerMain msg=""/>
  </div>
</template>

<script>
import ContainerMain from './components/ContainerMain.vue'

export default {
  name: 'App',
  components: {
    ContainerMain
  }
}
</script>

<style lang="scss">
  *{
    margin: 0;
    border: 0;
    box-sizing: border-box;
    color: white;
    font-family: 'Roboto', sans-serif;
  }
  #app {
    background-color: #14178b;
    min-height: 100vh;

  }
  
  header {
    text-align: center;
    img.logo {
      width: 33%;
      margin-top: 5vh;
      margin-bottom: 3vh;
    }
  }
</style>
