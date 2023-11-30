<script>
import AppCard from './components/AppCard.vue'
import axios from 'axios';

export default {
  components: {
    AppCard,

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
  }
}

</script>

<template>
  <main>

    <AppCard :arrayGenerato="beers" />
  </main>
</template>

<style scoped></style>
