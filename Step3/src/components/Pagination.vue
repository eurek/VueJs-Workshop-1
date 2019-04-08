<template>
  <nav aria-label="Page navigation example">
    <ul class="pagination">
      <li
        v-for="(beer, index) in numberOfPage"
        class="page-item"
      >
        <a @click="$emit('change-page', index)" class="page-link">{{index + 1}}</a>

      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'Pagination',
  props: {
    nbrResult: {
      type: Number
    }
  },
  computed: {
    numberOfPage () {
      return (Math.ceil(this.nbrResult / 10))
    }
  },
  methods: {

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.beers-list{
  min-height: 500px;
}
</style>
