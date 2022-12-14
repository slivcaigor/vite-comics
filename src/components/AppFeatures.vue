<script>
export default {
  data() {
    return {
      features: [
        {
          text: 'digital comics',
          icon: 'src/assets/img/buy-comics-digital-comics.png',
          alt: 'digital comics icon'
        },
        {
          text: 'dc merchandise',
          icon: 'src/assets/img/buy-comics-merchandise.png',
          alt: 'dc merchandise icon'
        },
        {
          text: 'subscription',
          icon: 'src/assets/img/buy-comics-subscriptions.png',
          alt: 'subscription icon'
        },
        {
          text: 'comic shop locator',
          icon: 'src/assets/img/buy-comics-shop-locator.png',
          alt: 'comic shop locator icon'
        },
        {
          text: 'dc power visa',
          icon: 'src/assets/img/buy-dc-power-visa.svg',
          alt: 'dc power visa icon'
        },
      ],
    }
  },
}
</script>

<template>
  <section class="features">
    <div class="container">
      <!-- v-for loop through an array of features and render a div element for each item in the array. -->
      <div v-for="(item, index) in features" :key="index" class="item">
        <!-- src and alt attribute, being dynamically bound to the icon and alt properties of the current item in the array. -->
        <img :src="item.icon" :alt="item.alt">
        <!-- double mustaches ({{}}) to insert the value of the text property of the current item in the array -->
        <h3>{{ item.text }}</h3>
      </div>
    </div>
  </section>
</template>


<style lang="scss" scoped>
@use '../styles/general.scss' as *;
@use '../styles/partials/mixins.scss' as *;
@use '../styles/partials/variables' as *;

.features {
  background-color: $accent;
  color: $primary;
  z-index: 77;
  position: relative;

  .container {
    display: flex;
    justify-content: space-between;
  }

  .item {
    @include center();
    padding: 3em 0;

    img {
      width: 3.75rem;
      height: 3.75rem;
      object-fit: contain;
      padding-right: .7em;
    }

    h3 {
      text-transform: uppercase;
      font-weight: 600;
      font-size: $text-nav;
    }
  }
}
</style>
