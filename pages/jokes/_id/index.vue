<template>
  <div>
    <nuxt-link to="/jokes"> Back To Jokes</nuxt-link>
    <h2>{{ joke }}</h2>
    <hr />
    <small>Joke ID: {{ $route.params.id }}</small>
  </div>
</template>

<script>
export default {}
</script>

<style></style>
