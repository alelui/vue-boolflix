<template>
    <header>
        <nav>
            <input type="text" v-model="queryTitle">
            <button @click="$emit('search',queryTitle)" >Cliccami</button>
        </nav>
    </header>
</template>

<script>
export default {
    name: 'Header',
    data(){
        return{
            queryTitle: ''
        }
    }
}
</script>

<style lang="scss" scoped>
    h2{
        color: blue;
    }
</style>