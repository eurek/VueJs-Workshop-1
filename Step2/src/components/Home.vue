<template>
  <div class="container">
    <div class="row card-group">

      <!-- BEER LIST -->
      <BeerList
        v-on:select-beer="selectedBeer = $event"
        :beers="beers">
      </BeerList>

      <!-- SELECTED BEER DETAILS -->
      <BeerDetails :beer="selectedBeer"></BeerDetails>
    </div>
  </div>
</template>

<script>
import BeerList from './BeerList'
import BeerDetails from './BeerDetails.vue'

export default {
  name: 'home',
  data () {
    return {
      beers: [],
      selectedBeer: {}
    }
  },
  mounted () {
    this.axios.get('https://api.punkapi.com/v2/beers', { params: { per_page: 80 } })
      .then(({data}) => {
        this.beers = data
      })
  },
  components: {
    BeerList,
    BeerDetails
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.beers-list{
  min-height: 500px;
}
</style>
