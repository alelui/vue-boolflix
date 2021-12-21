<template>
    <main>
        <MoviesList :films="films"/>
    </main>
</template>

<script>
import MoviesList from '../sections/MoviesList.vue';
export default {
    name: 'Main',
    components: {
        MoviesList
    },
    props:{
        films: Array
    }
}
</script>

<style lang="scss">
    h2{
        color: darkblue;
    }
    div{
        padding: 20px;
    }
</style>