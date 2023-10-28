<template>
  <div class="about">
    <Header/>
    <main class="page">
      <h1>about page</h1>
    </main>
  </div>
</template>

<script>

import Header from "@/components/Header.vue";

export default {
  name: 'AboutView',
  components: {
    Header
  },
}
</script>