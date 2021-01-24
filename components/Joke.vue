<template>
  <div class="joke">
    <p>{{ joke }}</p>

    <nuxt-link :to="'/jokes/' + id">
      <button>Click Me for ID</button>
    </nuxt-link>
  </div>
</template>

<script>
export default {
  name: 'Joke',
  props: ['joke', 'id'],
}
</script>

<style></style>
