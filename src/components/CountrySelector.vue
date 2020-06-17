<template lang="html">

    <div class="">
        <select v-model="selectedCountry" v-on:change="handleChange">
            <option v-for="(country, index) in countries" :country="country" :value="country" :key="index">{{country.name}}</option>
        </select>
    </div>

</template>

<script>

    import { eventBus } from '../main.js'


    export default {
        name: 'country-selector',
        data(){
            return {
                selectedCountry: null
            }
        },
        props: ['countries'],
        methods: {
            handleChange(){
                eventBus.$emit('selected-country', this.selectedCountry)
            }
        }
    }

</script>

<style lang="css" scoped>
</style>
