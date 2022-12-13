<script>
export default {
  props: {
    details: Object
  }
}
</script>

<template>


  <div class="cards">
    <img :src="details.thumb" :alt="details.series">
    <h3>{{ details.series }}</h3>
  </div>


</template>


<style lang="scss" scoped>
@use '../styles/general.scss' as *;
@use '../styles/partials/mixins.scss' as *;
@use '../styles/partials/variables' as *;

.cards {

  h3 {
    color: $primary;
    text-transform: uppercase;
    padding-top: .7em;
    font-size: 1rem;
  }
}
</style>
