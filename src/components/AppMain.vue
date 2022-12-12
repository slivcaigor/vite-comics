<script>

</script>

<template>

  <main class="main-content">
    <div class="container">
      <h1>🧑‍💻Content goes here👩‍💻</h1>
    </div>
  </main>

</template>


<style lang="scss" scoped>
@use '../styles/general.scss' as *;
@use '../styles/partials/mixins.scss' as *;
@use '../styles/partials/variables' as *;

.main-content {
  height: 500px;
  background-color: $secondary;
  color: $primary;

  h1 {
    @include center();
    height: 500px;
    font-size: $text-h1;
  }
}
</style>
