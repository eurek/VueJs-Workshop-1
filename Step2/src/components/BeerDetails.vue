<template>
  <div class="col-6 card pt-4">
    <h3>{{beer.name}}</h3>
    <div v-if="beer.image_url != null">
      <img height="300" width="100" v-bind:src="beer.image_url" alt="">
    </div>
  </div>
</template>

<script>
export default {
  props: ['beer'],
  name: 'BeerDetails'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.beers-list{
  min-height: 500px;
}
</style>
