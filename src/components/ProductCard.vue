<script>
export default {
  // a props object that defines a single property named details, which is expected to be an object.
  props: {
    details: Object
  }
}
</script>

<template>
  <div class="cards">
    <!-- src attribute and an alt attribute, both being dynamically bound to the component's details data property using the : prefix. -->
    <img :src="details.thumb" :alt="details.series">
    <!-- double mustaches ({{}}) to insert the values of the price and series properties of the details data property -->
    <h5>{{ details.price }}</h5>
    <h3>{{ details.series }}</h3>
    <!-- span text content is being set to the value of the type property of the details data property. -->
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
