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
    getImageURL: function (imgPath) {
      return new URL(imgPath, import.meta.url).href;
    }
  }
}
</script>

<template>
  <header>
    <a href="/">
      <img :src="getImageURL(`../assets/img/dc-logo.png`)" :alt="logo.logoAlt">
    </a>

    <nav>
      <ul>
        <li v-for="(link, index) in links" :key="index">
          <a :class="{ active: link.current }" href="#">
            {{ link.text }}
          </a>
        </li>
      </ul>
    </nav>
  </header>
</template>


<style lang="scss" scoped>

</style>
