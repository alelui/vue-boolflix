<template>
  <div id="app">
    <Header @search="searching"/>
    <Main :films="films"/>
    <Footer/>
  </div>
</template>

<script>
import axios from 'axios';
import Header from './components/macro/Header.vue'
import Main from './components/macro/Main.vue'
import Footer from './components/macro/Footer.vue'


export default {
  name: 'App',
  components: {
    Header,
    Main,
    Footer
  },
  data(){
    return{
      films: []
    }
  },
  methods:{
      searching(payload){
            axios.get('https://api.themoviedb.org/3/search/movie', {
                params: {
                api_key: '73feae1323429ea9ff64f7af3c1599ab',
                query: payload,
                language:'it-IT'
                }
            })
            .then((response) => {
                this.films = response.data.results
                console.log(this.films);
            })
            .catch((error) => {
                console.log(error);
            })
      }
  }
}
</script>

<style lang="scss">
  @import './assets/style/global.scss';
</style>
