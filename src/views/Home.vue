<template>
  <div class="home">
    <Header/>
    <main class="page">
      <h1>home page</h1>
    </main>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
export default {
  name: 'HomeView',
  components: {
    Header,
  }
}
</script>

<style lang="scss">
h1 {
  color: $red;
}
</style>
