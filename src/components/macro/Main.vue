<template>
    <main>
        <h3>Main</h3>
        <input type="text" v-model="queryTitle">
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
            queryTitle: ''
        }
    },
    methods:{
        search(){
            axios.get('https://api.themoviedb.org/3/search/movie', {
                params: {
                api_key: '73feae1323429ea9ff64f7af3c1599ab',
                query: this.queryTitle,
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