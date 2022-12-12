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
      footerSocials: [
        {
          image: 'src/assets/img/footer-facebook.png',
          url: '#',
          altText: 'Facebook Logo'
        },
        {
          image: 'src/assets/img/footer-twitter.png',
          url: '#',
          altText: 'Twitter Logo'
        },
        {
          image: 'src/assets/img/footer-youtube.png',
          url: '#',
          altText: 'YouTube Logo'
        },
        {
          image: 'src/assets/img/footer-pinterest.png',
          url: '#',
          altText: 'Pinterest Logo'
        },
        {
          image: 'src/assets/img/footer-periscope.png',
          url: '#',
          altText: 'Periscope Logo'
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
        <img :src="getImageURL(`../assets/img/dc-logo-bg.png`)" alt="DC Logo">
      </div>
    </div>
    <div class="container">
      <div>
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
      </div>

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

    <div class="footer-bottom">
      <div class="container socials-box">
        <a href="#">sign-up now&#33;</a>
        <div class="socials">
          <h4>follow us</h4>
          <div v-for="(social, index) in footerSocials" :key="index">
            <img :src="social.image" :alt="social.altText">
          </div>
        </div>
      </div>
    </div>

    <div class="bottom-bar"></div>
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
    right: 10%;

    img {
      max-width: 100%;
    }
  }

  nav:first-child {
    padding-bottom: 1em;
  }

  ul li {
    list-style-type: none;

    a {
      color: $footer-nav;
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
}

.footer-bottom {
  background-color: $third;
  z-index: 77;
  position: relative;

  a {
    color: $primary;
    text-transform: uppercase;
    font-size: 20px;
    font-weight: 600;
    padding: 12px;
    border: 2px solid $accent;
    text-decoration: none;
    margin-right: auto;
  }

  .socials {
    @include center(horizontal);
    gap: 1.2em;

    h4 {
      color: $accent;
      text-transform: uppercase;
      font-size: 1.4rem;
    }
  }

  .socials-box {
    padding: 30px 0;
  }
}

.bottom-bar {
  background-color: $secondary;
  height: 2em;
}
</style>
