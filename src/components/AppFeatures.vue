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
      <div v-for="(item, index) in features" :key="index" class="item">
        <img :src="item.icon" :alt="item.alt">
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

  .container {
    display: flex;
    justify-content: space-between;
  }

  .item {
    @include center();
    padding: 3em 0;

    img {
      width: 60px;
      height: 60px;
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
