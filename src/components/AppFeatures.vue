<script>
export default {
  methods: {
    // takes an imgPath parameter and returns the full URL of an image file based on the given imgPath
    getImageURL: function (imgPath) {
      // uses the URL constructor to create a new URL object based on the imgPath parameter and the import.meta.url property
      return new URL(imgPath, import.meta.url).href;
    }
  }
}

</script>

<template>

  <section class="features">
    <div class="container">

      <div class="item">
        <img :src="getImageURL(`../assets/img/buy-comics-digital-comics.png`)" alt="">
        <h3>digital comics</h3>
      </div>

      <div class="item">
        <img :src="getImageURL(`../assets/img/buy-comics-merchandise.png`)" alt="">
        <h3>dc merchandise</h3>
      </div>

      <div class="item">
        <img :src="getImageURL(`../assets/img/buy-comics-subscriptions.png`)" alt="">
        <h3>subscription</h3>
      </div>

      <div class="item">
        <img :src="getImageURL(`../assets/img/buy-comics-shop-locator.png`)" alt="">
        <h3>comic shop locator</h3>
      </div>

      <div class="item">
        <img :src="getImageURL(`../assets/img/buy-dc-power-visa.svg`)" alt="">
        <h3>dc power visa</h3>
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
