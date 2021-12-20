<template>
    <main>
        <h3>Main</h3>
        <input type="text">
        <button @click="search" >Cliccami</button>
    </main>
</template>

<script>
import axios from 'axios';
export default {
    name: 'Main',
    data(){
        return{
            movies: null,
        }
    },
    methods:{
        search(){
            axios.get('https://api.themoviedb.org/3/search/movie', {
                params: {
                api_key: '73feae1323429ea9ff64f7af3c1599ab',
                query: 'ritorno',
                language:'it-IT'
                }
            })
            .then((response) => {
                this.movies = response.data.results
                console.log(this.movies);
            })
            .catch((error) => {
                console.log(error);
            })
        }
    }
}
</script>

<style lang="scss" scoped>
    h3{
        color: red;
    }
</style>