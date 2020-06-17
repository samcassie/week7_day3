<template lang="html">
    <li v-on:click="handleClick">{{country.name}}</li>
</template>

<script>

    import { eventBus } from '../main.js'

    export default {
        name: 'countries-list-item',
        props: ['country'],
        methods: {
            handleClick(){
                eventBus.$emit('selected-country', this.country)
            }
        }

    }
</script>

<style lang="css" scoped>
</style>
