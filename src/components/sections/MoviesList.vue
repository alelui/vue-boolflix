<template>
  <section>
        <div v-for="film in films" :key="film.id">
          <Card :info="film"/>
        </div>
  </section>
</template>

<script>
import Card from '../elements/Card.vue'
export default {
    name: 'MoviesList',
        props:{
        films: Array
    },
    components:{
      Card
    }

}
</script>

<style>

</style>