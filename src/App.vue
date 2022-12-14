<script>
import AppHeader from './components/AppHeader.vue'
import AppFooter from './components/AppFooter.vue'
import AppMain from './components/AppMain.vue'
import AppHero from './components/AppHero.vue'

export default {
  components: {
    AppHeader,
    AppFooter,
    AppMain,
    AppHero
  }
}
</script>

<template>
  <header>
    <AppHeader />
    <AppHero />
  </header>

  <main>
    <AppMain />
  </main>

  <footer>
    <AppFooter />
  </footer>

</template>

<style lang="scss" scoped>
@use './styles/general.scss' as *;
@use './styles/partials/mixins' as *;
@use './styles/partials/variables' as *;
</style>
