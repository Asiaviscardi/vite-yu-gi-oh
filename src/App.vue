<script>
import axios from 'axios';
import Header from './components/Header.vue';
import Main from './components/Main.vue';
export default {
  components:{
    Header,
    Main
  }

}
</script>

<template>

  <Header/>

  <Main/>
  
</template>

<style lang="scss">

body{
  background-color: #D48F38;
}

</style>