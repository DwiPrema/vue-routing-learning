<script setup>
import { RouterView } from "vue-router"
</script>

<template>
  <main>
    <div class="links">
      <a href="/">Home</a>
      <a href="/about">About</a>
    </div>
    <RouterView />
  </main>
</template>

<style scoped>
.links {
    padding: 20px
}

.links a {
    margin: 0 5px
}
</style>