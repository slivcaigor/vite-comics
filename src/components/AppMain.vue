<script>
import ProductCard from './ProductCard.vue'

export default {
  components: {
    ProductCard
  },
  data() {
    return {
      cards: [
        {
          "thumb": "https://www.dccomics.com/sites/default/files/styles/covers192x291/public/comic-covers/2018/09/AC1000_DLX_162-001_HD_5ba13723281ab0.37845353.jpg?itok=ZsI-C5eX",
          "price": "$19.99",
          "series": "Action Comics",
          "type": "comic book"
        },
        {
          "thumb": "https://www.dccomics.com/sites/default/files/styles/covers192x291/public/comic-covers/2020/09/AV1976_01_300-001_HD_5f738f6e39ddd7.18205602.jpg?itok=VgdYdJ01",
          "price": "$3.99",
          "series": "American Vampire 1976",
          "type": "comic book"
        },
        {
          "thumb": "https://www.dccomics.com/sites/default/files/styles/covers192x291/public/gn-covers/2018/08/AQMv4_UW_153-001_HD_5b7efa1745a9b8.08589135.jpg?itok=HPTtnrsb",
          "price": "$16.99",
          "series": "Aquaman",
          "type": "graphic novel"
        },
        {
          "thumb": "https://www.dccomics.com/sites/default/files/styles/covers192x291/public/comic-covers/2018/06/batgirl_v5_1_5b23e1f1124941.50950783.jpg?itok=VnrJah76",
          "price": "$2.99",
          "series": "Batgirl",
          "type": "comic book"
        },
        {
          "thumb": "https://www.dccomics.com/sites/default/files/styles/covers192x291/public/comic-covers/2018/09/BM_56_300-001_HD_5ba137a85c3bf3.33122291.jpg?itok=3FHJQYJZ",
          "price": "$3.99",
          "series": "Batman",
          "type": "comic book"
        },
        {
          "thumb": "https://www.dc.com/sites/default/files/styles/covers192x291/public/comic-covers/2018/06/batman_657_5b11847b0026d3.30559057.jpg?itok=sqWnbFnx",
          "price": "$2.99",
          "series": "Batman and Son",
          "type": "comic book"
        },
        {
          "thumb": "https://www.dccomics.com/sites/default/files/styles/covers192x291/public/comic-covers/2019/08/BMSM_5d4361b7116261.74371456.jpg?itok=kEDR2OL8",
          "price": "$3.99",
          "series": "Batman/Superman",
          "type": "comic book"
        },
        {
          "thumb": "https://www.dccomics.com/sites/default/files/styles/covers192x291/public/comic-covers/2020/09/BMSMANN_01_300-001_HD_5f5ff17fa1d665.74704970.jpg?itok=azz5sfGk",
          "price": "$4.99",
          "series": "Batman/Superman Annual",
          "type": "comic book"
        },
        {
          "thumb": "https://www.dccomics.com/sites/default/files/styles/covers192x291/public/comic-covers/2020/09/BMTJWZ_01_300-001_HD_5f5ff2307dcb37.34652945.jpg?itok=VswVjLR8",
          "price": "$5.99",
          "series": "Batman: The Joker War Zone",
          "type": "comic book"
        },
        {
          "thumb": "https://www.dccomics.com/sites/default/files/styles/covers192x291/public/comic-covers/2020/08/cover-v2_5f40314645a734.37285065.png?itok=ImNM2QBY",
          "price": "$6.99",
          "series": "Batman: Three Jokers",
          "type": "comic book"
        },
        {
          "thumb": "https://www.dccomics.com/sites/default/files/styles/covers192x291/public/comic-covers/2020/10/BMWK_HQ_01_300-001_HD_5f7cb4945e13f6.89501032.jpg?itok=sVwALbUX",
          "price": "$4.99",
          "series": "Batman: White Knight Presents: Harley Quinn",
          "type": "comic book"
        },
        {
          "thumb": "https://www.dccomics.com/sites/default/files/styles/covers192x291/public/gn-covers/2019/04/CTWv1_CC_144-001_HD_5ca5299a751963.53054221.jpg?itok=ooPaoLDq",
          "price": "$16.99",
          "series": "Catwoman",
          "type": "graphic novel"
        }
      ]
    }
  }
}
</script>

<template>

  <section class="main-content">
    <div class="container">
      <div class="series">
        <h2>current series</h2>
      </div>


      <div class="thumbs">
        <!-- v-for to loop through an array of cards and render a ProductCard component -->
        <!-- :key attribute used to assign a unique key to each item in the array -->
        <!-- :details attribute used to pass the details of the current card to the ProductCard component -->
        <ProductCard v-for="(card, index) in cards" :key="index" :details="card" class="card" />
      </div>
      <div class="more">
        <a class="btn" href="#">load more</a>
      </div>
    </div>
  </section>
</template>


<style lang="scss" scoped>
@use '../styles/general.scss' as *;
@use '../styles/partials/mixins.scss' as *;
@use '../styles/partials/variables' as *;

.container {
  position: relative;

  .series {
    position: absolute;
    top: -2em;
    left: -2em;

    h2 {
      color: $primary;
      text-transform: uppercase;
      font-size: 1.8rem;
      font-weight: 600;
      padding: 0.5em 1em;
      background-color: $accent;
    }
  }
}

.main-content {
  background-color: $secondary;

  .more {
    text-align: center;
    padding-bottom: 2em;

    .btn {
      color: $primary;
      text-transform: uppercase;
      font-size: .9rem;
      font-weight: 600;
      padding: 0.75em 3em;
      text-decoration: none;
      background-color: $accent;
    }
  }

  .thumbs {
    display: flex;
    flex-wrap: wrap;
    padding: 5em 0;
    gap: 1.5em;

    .card {
      width: calc(100% / 6 - 1.25em);
    }
  }
}
</style>
