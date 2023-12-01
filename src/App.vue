<script>
import AppCard from './components/AppCard.vue'
import AppSearch from './components/AppSearch.vue'
import { store } from "./store.js" //state management
import axios from 'axios';

export default {
  components: {
    AppCard,
    AppSearch
  },
  data() {

    return {
      beers: ""
    }
  },

  mounted() {
    this.getBeer();
  },

  methods: {
    getBeer() {
      axios.get('https://api.openbrewerydb.org/v1/breweries?by_country=poland&per_page=10').then(risultato => {
        this.beers = risultato.data
      })

    }
  },


  getAppCard() {
    this.beers = ""
    axios.get(`https://api.openbrewerydb.org/v1/breweries?by_country=poland&by_name=${store.searchString}`).then(risultato => {
      this.beers = risultato.data
    })


  }

}

</script>

<template>
  <header>
    <AppSearch @search="getAppCard" />
  </header>
  <main>
    <AppCard :arrayGenerato="beers" />
  </main>
</template>

<style scoped></style>
