<template lang="html">

    <div class="">
        <ul>
            <countries-list-item v-for="(country, index) in countries" :country="country" :key="index"></countries-list-item>
        </ul>
    </div>

</template>

<script>

    import CountriesListItem from './CountriesListItem.vue';

    export default {
        name: 'countries-list',
        props: ['countries'],
        components: {
            "countries-list-item": CountriesListItem
        }
    }

</script>

<style lang="css" scoped>
</style>
