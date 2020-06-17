<template lang="html">

    <div class="">
        <h1>Countries</h1>
        <div class="">
            <country-selector :countries='countries'></country-selector>
            <selected-country :country='selectedCountry'></selected-country>
        </div>
    </div>

</template>

<script>

    // import CountriesList from './components/CountriesList.vue';
    import { eventBus } from './main.js'
    import SelectedCountry from './components/SelectedCountry.vue'
    import CountrySelector from './components/CountrySelector.vue'

    export default {

        name: 'app',
        data(){
            return {
                countries: [],
                selectedCountry: null
            };
        },
        mounted(){
            fetch('https://restcountries.eu/rest/v2/all')
            .then(res => res.json())
            .then(countries => this.countries = countries)

            eventBus.$on('selected-country', (country) => {
                this.selectedCountry = country
            })
        },
        components: {
            "country-selector": CountrySelector,
            // "countries-list": CountriesList,
            "selected-country": SelectedCountry
        }
    }

</script>


<style lang="css" scoped>
</style>
