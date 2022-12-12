<script>
import AppFeatures from './AppFeatures.vue'

export default {
  components: {
    AppFeatures
  },
  data() {
    return {
      footerFirstNav: [
        {
          heading: 'dc comics',
        },
        {
          text: 'Characters',
          url: '#',
        },
        {
          text: 'Comics',
          url: '#',
        },
        {
          text: 'Movies',
          url: '#',
        },
        {
          text: 'TV',
          url: '#',
        },
        {
          text: 'Games',
          url: '#',
        },
        {
          text: 'Videos',
          url: '#',
        },
        {
          text: 'News',
          url: '#',
        }
      ],
      footerSecondNav: [
        {
          heading: 'shop',
        },
        {
          text: 'Shop DC',
          url: '#',
        },
        {
          text: 'Shop DC Collectibles',
          url: '#',
        },
      ],
      footerThirdNav: [
        {
          heading: 'DC',
        },
        {
          text: 'Terms of Use',
          url: '#',
        },
        {
          text: 'Privacy Policy (NEW)',
          url: '#',
        },
        {
          text: 'Ad Choices',
          url: '#',
        },
        {
          text: 'Advertising',
          url: '#',
        },
        {
          text: 'Jobs',
          url: '#',
        },
        {
          text: 'Subscriptions',
          url: '#',
        },
        {
          text: 'Talent Workshops',
          url: '#',
        },
        {
          text: 'CPSC Certificates',
          url: '#',
        },
        {
          text: 'Ratings',
          url: '#',
        },
        {
          text: 'Shop Help',
          url: '#',
        },
        {
          text: 'Contact Us',
          url: '#',
        },
      ],
      footerForthNav: [
        {
          heading: 'sites',
        },
        {
          text: 'dC',
          url: '#',
        },
        {
          text: 'MAD Magazine',
          url: '#',
        },
        {
          text: 'DC Kids',
          url: '#',
        },
        {
          text: 'DC Universe',
          url: '#',
        },
        {
          text: 'DC Power Visa',
          url: '#',
        },
      ],
    }
  },
  methods: {
    // takes an imgPath parameter and returns the full URL of an image file based on the given imgPath
    getImageURL: function (imgPath) {
      // uses the URL constructor to create a new URL object based on the imgPath parameter and the import.meta.url property
      return new URL(imgPath, import.meta.url).href;
    },
  }
}
</script>

<template>
  <AppFeatures />

  <footer>
    <div class="bg-image">
      <div class="overlay-image">
        <img src="../assets/img/dc-logo-bg.png" alt="">
      </div>
    </div>
    <div class="container">
      <nav>
        <ul>
          <li v-for="(link, index) in footerFirstNav" :key="index">
            <h3>{{ link.heading }}</h3>
            <a href="#">
              {{ link.text }}
            </a>
          </li>
        </ul>
      </nav>

      <nav>
        <ul>
          <li v-for="(link, index) in footerSecondNav" :key="index">
            <h3>{{ link.heading }}</h3>
            <a href="#">
              {{ link.text }}
            </a>
          </li>
        </ul>
      </nav>

      <nav>
        <ul>
          <li v-for="(link, index) in footerThirdNav" :key="index">
            <h3>{{ link.heading }}</h3>
            <a href="#">
              {{ link.text }}
            </a>
          </li>
        </ul>
      </nav>

      <nav>
        <ul>
          <li v-for="(link, index) in footerForthNav" :key="index">
            <h3>{{ link.heading }}</h3>
            <a href="#">
              {{ link.text }}
            </a>
          </li>
        </ul>
      </nav>
    </div>


    <div class="footer-bottom"></div>
  </footer>

</template>


<style lang="scss" scoped>
@use '../styles/general.scss' as *;
@use '../styles/partials/mixins.scss' as *;
@use '../styles/partials/variables' as *;

footer {
  background-position: top;
  background-size: cover;
  background-repeat: no-repeat;
  background-image: url("../assets/img/footer-bg.jpg");

  .bg-image {
    position: relative;
  }

  .overlay-image {
    position: absolute;
    top: -50px;
    right: 5%;
    z-index: 1;

    img {
      max-width: 100%;
    }
  }

  ul li {
    list-style-type: none;

    a {
      color: $primary;
      text-decoration: none;
      text-transform: capitalize;
    }

    h3 {
      color: $primary;
      text-transform: uppercase;
      font-size: 24px;
      padding-bottom: .3em;
    }
  }

  .container {
    padding: 50px 0;
    display: flex;
    gap: 20px;
  }


  .footer-bottom {
    background-color: $secondary;
    height: 180px;
    z-index: 77;
    position: relative;
  }
}
</style>
