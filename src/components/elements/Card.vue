<template>
  <section>
        <h2>{{info.title}}</h2>
        <p><strong>Original title => </strong>{{info.original_title}}</p>
        <p><strong>Original language => </strong>{{info.original_language}}</p>
        <p><strong>Vote => </strong>{{info.vote_average}}</p>
  </section>
</template>

<script>
export default {
    name: 'Card',
    props:{
        info: Object
    }
}
</script>

<style>

</style>