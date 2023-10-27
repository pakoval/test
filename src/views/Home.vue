<template>
  <div class="home">
    <h1>Home page</h1>
    <nav>
      <router-link to="/about">About</router-link>
    </nav>
    <img alt="Vue logo" src="../assets/logo.png">
  </div>
</template>

<script>
export default {
  name: 'HomeView',
}
</script>

<style lang="scss">
h1 {
  color: $red;
}
</style>
