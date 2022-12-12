<script>
export default {
  data() {
    return {
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
      logo:
      {
        logoAlt: 'DC Comics Logo'
      }
    }
  },
  methods: {
    // takes an imgPath parameter and returns the full URL of an image file based on the given imgPath
    getImageURL: function (imgPath) {
      // uses the URL constructor to create a new URL object based on the imgPath parameter and the import.meta.url property
      return new URL(imgPath, import.meta.url).href;
    },
    clicked(index) {
      // takes an index parameter, which is the index of the clicked menu item
      this.links.forEach((item, i) => {
        // sets the current property of a menu item to true if the index of the current item in the forEach() loop is the same as the index parameter passed to the method
        item.current = index === i;
      });
    }
  }
}
</script>

<template>
  <div class="top-bar"></div>
  <div class="container">
    <header>
      <a href="/">
        <!-- return the full URL of the image file -->
        <img :src="getImageURL(`../assets/img/dc-logo.png`)" :alt="logo.logoAlt">
      </a>

      <nav>
        <ul>
          <!-- v-for loop that iterates over an array of objects called links -->
          <li v-for="(link, index) in links" :key="index">
            <!-- For each object in the links array, it creates a <li> element that contains an <a> element -->
            <!-- The <a> element has the active class applied to it if the current property of the link object is true. -->
            <!-- @click event listener that calls the clicked() method with the index of the link object as an argument -->
            <a :class="{ active: link.current }" href="#" @click="clicked(index)">
              {{ link.text }}
            </a>
          </li>
        </ul>
      </nav>
    </header>
  </div>
</template>


<style lang="scss" scoped>
@use '../styles/general.scss' as *;
@use '../styles/partials/mixins.scss' as *;
@use '../styles/partials/variables' as *;

.active {
  border-bottom: 4px solid $accent;
}

.top-bar {
  background-color: $secondary;
  height: 2em;
}

header {
  margin-top: 1.5rem;
  @include center();

  a:first-child {
    margin-right: auto;
  }

  img {
    width: 70%;
  }
}

ul {
  list-style-type: none;
  @include center();

  li a {
    display: inline-block;
    text-decoration: none;
    font-size: $text-nav;
    font-weight: 600;
    text-transform: uppercase;
    color: $third;
    padding: 1rem;

    &.active,
    &:hover {
      color: $accent;
    }
  }
}
</style>
