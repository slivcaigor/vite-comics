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
    <h5>{{ details.price }}</h5>
    <h3>{{ details.series }}</h3>
    <span class="label">{{ details.type }}</span>
  </div>


</template>


<style lang="scss" scoped>
@use '../styles/general.scss' as *;
@use '../styles/partials/mixins.scss' as *;
@use '../styles/partials/variables' as *;

.cards {
  position: relative;

  &:hover .label {
    visibility: visible;
  }

  .label {
    visibility: hidden;
    top: 5%;
    right: 0;
    position: absolute;
    background-color: $accent;
    padding: .2em .5em;
    color: $primary;
    font-size: 1rem;
    font-weight: 600;
    text-transform: uppercase;
  }

  h5 {
    color: $accent;
    text-transform: uppercase;
    padding-top: .2em;
    font-size: 1rem;
  }

  h3 {
    color: $primary;
    text-transform: uppercase;
    font-size: 1rem;
    padding-top: .2em;
  }
}
</style>
