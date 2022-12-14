<script>
export default {
  data() {
    return {
      activeItem: 0,
      links: [
        {
          text: 'Characters',
          url: '#',
          current: true,
        },
        {
          text: 'Comics',
          url: '#',
          current: false,
        },
        {
          text: 'Movies',
          url: '#',
          current: false,
        },
        {
          text: 'TV',
          url: '#',
          current: false,
        },
        {
          text: 'Games',
          url: '#',
          current: false,
        },
        {
          text: 'Collectibles',
          url: '#',
          current: false,
        },
        {
          text: 'Videos',
          url: '#',
          current: false,
        },
        {
          text: 'Fans',
          url: '#',
          current: false,
        },
        {
          text: 'News',
          url: '#',
          current: false,
        },
        {
          text: 'Shop',
          url: '#',
          current: false,
        }
      ],
    }
  },
  methods: {
    // takes an imgPath parameter and returns the full URL of an image file based on the given imgPath
    getImageURL: function (imgPath) {
      // uses the URL constructor to create a new URL object based on the imgPath parameter and the import.meta.url property
      return new URL(`../assets/img/${imgPath}`, import.meta.url).href;
    },
  },
}
</script>

<template>
  <div class="top-bar"></div>
  <div class="container">
    <section>
      <a href="/">
        <!-- return the full URL of the image file -->
        <img :src="getImageURL(`dc-logo.png`)" alt="DC Comics Logo">
      </a>
      <nav>
        <ul>
          <!-- v-for loop that iterates over an array of objects called links -->
          <li v-for="(link, index) in links" :key="index">
            <!-- For each object in the links array, it creates a <li> element that contains an <a> element -->
            <!-- The <a> element has the active class applied to it if the current property of the link object is true. -->
            <a :class="{ active: index === activeItem }" href="#" @click="activeItem = index">
              {{ link.text }}
            </a>
          </li>
        </ul>
      </nav>
    </section>
  </div>
</template>


<style lang="scss" scoped>
@use '../styles/general.scss' as *;
@use '../styles/partials/mixins.scss' as *;
@use '../styles/partials/variables' as *;

.active {
  border-bottom: 0.25rem solid $accent;
}

.top-bar {
  background-color: $secondary;
  height: 2em;
}

section {
  margin: 1.5rem 0;
  @include center();

  a:first-child {
    margin-right: auto;
  }

  img {
    width: 80%;
  }
}

ul {
  list-style-type: none;
  @include center();
  gap: 2em;

  li a {
    display: inline-block;
    text-decoration: none;
    font-size: $text-nav;
    font-weight: 600;
    text-transform: uppercase;
    color: $third;
    padding: .5em 0;

    &.active,
    &:hover {
      color: $accent;
    }
  }
}
</style>
