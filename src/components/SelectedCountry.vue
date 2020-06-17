<template lang="html">

    <div v-if='country'>
        <h3>{{country.name}}</h3>
        <p>Population: {{country.population}}</p>

    </div>

</template>

<script>

    import { eventBus } from '../main.js'

    export default {
        name: 'selected-country',
        props: ['country']
    }

</script>

<style lang="css" scoped>
</style>
