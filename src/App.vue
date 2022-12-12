<script>
import AppHeader from './components/AppHeader.vue'
import AppFooter from './components/AppFooter.vue'
import AppFeatures from './components/AppFeatures.vue'
import AppMain from './components/AppMain.vue'

export default {
  components: {
    AppHeader,
    AppFooter,
    AppFeatures,
    AppMain
  }
}
</script>

<template>
  <AppHeader />
  <AppMain />
  <AppFooter />

</template>

<style lang="scss" scoped>
@use './styles/general.scss' as *;
@use './styles/partials/mixins' as *;
@use './styles/partials/variables' as *;
</style>
