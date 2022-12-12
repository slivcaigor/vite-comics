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
  background-image: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url("../assets/img/jumbotron.jpg");
}

h1 {
  @include center();
  height: 31.25rem;
  font-size: $text-h1;
  color: $primary;
}
</style>
